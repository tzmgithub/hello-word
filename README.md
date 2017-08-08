# hello-word
新世界的大门
<style>
  #main{
    margin:0;
    padding:10px;
    background-color: #2A3542;
    min-height: 100px;
    width:188px;
}
#main h3{
    margin:0;
    padding:5px 0 0 10px;
    border-top-left-radius: 3px;
    border-top-right-radius: 3px;
    cursor: pointer;
    line-height: 30px;
}
#main .ah3{
    text-decoration:none;
    color:#AEB2B7;
    font-size: 16px;
}
#main .uList{
    list-style:none;
    margin-top:0;
    padding:10px 0 10px 30px;
    background-color: #35404D;
    border-radius: 3px;
    display:none;
}
#main .uList li{
    color:#AEB2B7;
    cursor: pointer;
}
#main h3>a{
    display:inline-block;
    width:188px;
    height:36px;
    padding-left:10px;
    box-sizing: border-box;
}
</style>
<body>
  <div id="main">
      <h3>
          <a href="#" class="ah3">商品列表</a>
          <span style="display:none">0</span>
      </h3>
      <ul class="uList">
          <li>添加新商品</li>
          <li>商品分类</li>
          <li>用户评论</li>
          <li>商品回收</li>
          <li>库存管理</li>
      </ul>
      <h3>
          <a href="#" class="ah3">订单管理</a>
          <span style="display:none">0</span>
      </h3>
      <ul class="uList">
          <li>商品订单1</li>
          <li>商品订单2</li>
          <li>商品订单3</li>
          <li>商品订单4</li>
          <li>商品订单5</li>
      </ul>
      <h3>
          <a href="#" class="ah3">电视管理</a>
          <span style="display:none">0</span>
      </h3>
      <ul class="uList">
          <li>电汇1</li>
          <li>电汇2</li>
          <li>电汇3</li>
          <li>电汇4</li>
          <li>电汇5</li>
      </ul>
  </div>
  <script>
    $("#main>h3").on("click", function (e) { //上滑隐藏下滑显示
          e.stopPropagation();
      //如果span为0 那么被点击的目标中的span为1，被点击目标的兄弟中的span变为0
          if($(this).find("span").html()==0){
              $(this).find("span").html(1);
              $(this).siblings().find("span").html(0);
          }else if($(this).find("span").html()==1){
              //如果被点击的目标中的span为1，那么就进行改变
              $(this).find("span").html(0);
          }

          $(this).parent().find("ul").slideUp();

          if($(this).find("span").html()==1){
          //如果被点击的目标的span为1，那么就向下展开
              $(this).next().slideDown();
          }else if($(this).find("span").html()!=1){
          //如果被点击的目标的span不为1，那么就向上隐藏
              $(this).next().slideUp();
          }
          $(this).parent().find("h3").css("backgroundColor","#2A3542");
          $(this).css("backgroundColor","#35404D");
      });
  </script>
</body>
