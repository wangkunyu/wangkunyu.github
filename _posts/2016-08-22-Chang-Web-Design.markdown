---
layout:     post
title:      "Chang哥教你写Web(一)：如何设计一个简单的静态网页"
subtitle:   "" 
date:       2016-08-22 14:35:35 +0200
author:     "AlbertWu"
header-img: "img/post-bg-web.jpg"
tags:
    - html+css
---

# 制作主题为《钢炼FA》的简易静态网页

男神镇楼！
![alt text](https://cn-albertwu96.github.io/img/webStart.jpg "Edward Elric")

谈到钢炼，想必是很多热血青年初中时候追的番之一！然而Zang哥我却不得不承认初中时候天天学chui习bi，错过了这么一部主角有热血，配角有尊严，剧情无尿点，boss无解肥的热血番剧。[[老司机带你上车]](http://www.bilibili.com/video/av5563910/)

[扯远了](https://wangkunyu.github.io/documents/test.pdf) 这篇博客主要是记录一下自己写[网页](http://codepen.io/CN-AlbertWu96/full/EyrKmG/)的痛苦历程，也为了归纳一下自己的学习心得吧。

首先无论写什么网站都有其**固定格式**

```
<!DOCTYPE html>
<html>
<head>
  <title>    </title>
  <!--此处填写页面主题，会出现在网页的标签中
   head中经常需要申明引入第三方库，譬如javascript,css,jquery等
  <script type="text/javascript" src="js/d3.v3.js"></script>
  <link rel="stylesheet" href="css/display.css"> -->
</head>
<body>
<!-- body就是给你大展拳脚，肆意玩耍的地方啦 -->
</body>
</html>
```

然后我会分成四大块来讲述我写的网页的构成(**本网页是基于[bootstrap](http://v3.bootcss.com/css/)的层叠样式表建立，独立的css格式会有相应说明**)
- 导航栏
- 主页面
- 缩略图
- 尾页

## 导航栏(navigation 简称nav)
![alt text](https://cn-albertwu96.github.io/img/webNavigation.png "navigation")

```html
<!-- Navigation -->
  <nav class="navbar navbar-default navbar-fixed-top topnav">
  <!-- 确保此nav使用bootstrap的navbar样式,topnav修改了nav中的字体以及背景样式 -->
    <div class="container topnav">
    <!-- 在当前nav中建立一个容器container -->
      <div class="navbar-header">
        <a class="navbar-brand topnav" href="#">Albert Wu</a>
        <!-- #表示链接至当前页面，不向外引用 -->
      </div>
      <div class="collapse navbar-collapse">
        <ul class="nav navbar-nav navbar-right">
          <li><a href="#home">Home</a></li>
          <li><a href="#character">Character</a></li>
          <li><a href="#plot">Plot</a></li>
        </ul>
      </div>
    </div>
    <!-- 容器完成 -->
    </nav>
```

## 主页面(name="home")
![alt text](https://cn-albertwu96.github.io/img/webHome.png "home")

```html
<a name="home"></a>
<!-- name用于href中的页面内跳转 <li><a -->href="#home"<!-- >Home</a></li> -->
      <div class="intro-header">
      <!-- intro-header中设置页面大小，背景，填充Padding以及边缘Margin大小,在background中fixed可以使得页面在拖拽中有翻书的感觉
      This keyword means that the background is fixed with regard to the viewport. Even if an element has a scrolling mechanism, a ‘fixed’ background doesn't move with the element. -->
        <div class="container">
          <div class="row">
            <div class="col-lg-12">
            <!-- 此处值得一提bootstrap把页面分成了多个栅格，譬如class="col-lg-12"就是指以下div横向拓展为12个栅格，利用col-lg-offset-?可以使得其右移？个栅格 -->
              <div class="intro-message"> 
                <h1>FullMetal Alchemist</h1>
                <h3>鋼の錬金術師</h3>
                <hr class="intro-divider">
                  <ul class="list-inline">
                  <!-- inline与block[对应](http://www.cnblogs.com/jdonson/archive/2011/06/10/2077932.html)，前者表示元素都在一行，后者表示元素各自为一块，分行 -->
                    <li><a href="http://fa.ffsky.cn/char_winry.htm" class="btn btn-default btn-lg"><i class="fa fa-male fa-fw"></i><!-- 添加[Awesome Icon](http://fontawesome.io/3.2.1/icons/)的按钮 --><span>Character</span></a></li>
                    <li class="block"><a href="http://www.dilidili.com/anime/hagaren/story/" class="btn btn-default btn-lg"><i class="fa fa-info fa-fw"></i><span>Plot</span></a></li>
                    <li class="block"><a href="http://music.163.com/#/playlist?id=37157030" class="btn btn-default btn-lg"><i class="fa fa-music fa-fw"></i><span>Music</span></a></li>
                </ul>
              </div>
            </div>
          </div>
        </div>
  </div>
```

## 缩略图
![alt text](https://cn-albertwu96.github.io/img/webPortfolio.png "portfolio")

```html
<div class="row">
          <div class="col-md-4 col-sm-6 portfolio-item">
          <!-- 此处表示以下div在中等放缩情况下占4栅格，小等级放缩情况下占6栅格 -->
            <a href="http://www.xiaozhan.cc/watch/9902/" target="_blank" class="portfolio-link">
              <div class="portfolio-hover">
                <div class="portfolio-hover-content">
                  <i class="fa fa-fire fa-4x"></i>
                </div>
              </div>
              <img src="https://encrypted-tbn3.gstatic.com/images?q=tbn:ANd9GcQqpPbHNfHQdOaVkdwdvp6bClLdo0YnS240iUwGV28HAc9y6_1M" class="img-responsive" alt="第二集">
            </a>
            <div class="portfolio-caption">
              <h4> 第2话「开端之日」</h4>
            </div>
          </div>
</div>
```

## 尾页
![alt text](https://cn-albertwu96.github.io/img/webFooter.png "footer")

```html
<footer class="text-center">
  <div class="container">
        <ul class="list-inline">
        <!-- 内联插入多个尾列表 -->
          <li><a href="#home"><i class="fa fa-home"></i><span> Home</span></a></li>
          <li><a href="#character"><i class="fa fa-male"></i><span> Character</span></a></li>
          <li><a href="#plot"><i class="fa fa-info"></i><span> Plot</span></a></li>
        </ul>
        <p class="copyright text-muted small">Copyright &copy; Albert Wu Desing 2016. All Rights Reserved</p>
        <!-- 页尾记得写明copyright -->
    </div>
  </div>
```

写了这么多备注，累死本Zang了，真心强烈推荐钢炼FA啊！！！注FA与非FA差别在于悲?喜剧结尾。
“**等价交换**”的核心思想贯穿全篇，没有说教，没有直接讲大道理，也没有很bug的魔法大招，有的只是各自的“心怀鬼胎”以及部分人的“正义”。
感谢各位看官的浏览。

# 欢迎评论