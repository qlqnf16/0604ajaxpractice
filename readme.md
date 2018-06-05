# AJAX 활용

### jQuery로 AJAX를 이용해 JSON 파일을 가져오고, 가공하기
```
<script>
    $("button").click(function() {
        $.ajax({
            url: "https://dog.ceo/api/breeds/image/random",
            dataType: "json",
            success: function (a) {
                $("img").attr("src", a["message"])
            }
        });
    })
</script>
```

* button을 클릭하면 ajax를 사용한다.
* url: 정보를 가져올 서버 주소 (URL이 될 수도 있고, post_path같은 route가 될 수도 있다)
* dataType: 가져오는 정보의 형태
* success: 서버에 성공적으로 접속하고 수행할 function을 지정한다

가져온 정보는 __a__에 담긴다. json API에 접근하던 것과 같은 방식으로 원하는 정보에 접근하고, _(이번 과제의 경우 message에 담겨있는 이미지 주소)_ 그 정보를 알맞게 이용하면 된다. 이번 과제의 경우 이미지를 불러와야 했기 때문에 미리 body에 `<img></img>`를 지정해놓고 img의 attribute를 가져온 정보`a["message"]`로 수정했다. 이렇게 하는거 맞겠지^^....!
