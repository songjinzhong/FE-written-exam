# FE-written-exam

我总结的前端笔试题，自己写的！

校招内推的笔试快要开始了，最近陆续收到笔试的通知，尽管内推还在进行中。。（2017.3.18）

感觉是时候准备一下笔试的东西，虽然之前内推二面的时候让我用白纸手撸算法（冒泡）和正则表达式，我也是迫不及防呀。

以下面试题均来自互联网，我会尽量贴上链接的。

## 2014 阿里巴巴前端实习招聘

先来 [2014真题](http://www.cnblogs.com/ayqy/p/4376465.html)。

ps：以下均为个人解法，正误未知，请谨慎！

### 1

>请在触摸屏下实现一个按钮，当按快速触碰按钮并放开手时，立刻弹出“成功”二字的提示框。

首先，看到触屏端，我是懵逼的，自己没有写过触屏端的点击事件，而且还是**快速触碰，并放开手**，难道不是用 click？？

貌似用的 `touchend`：

```html
<button id="btn">Click Me</button>

<script type="text/javascript">
var btn = document.getElementById("btn");
btn.addEventListener("touchend", function(){
  alert("成功");
}, false)
</script>
```

### 2

>请封装一个名叫Counter的计数器Class，只有两个公有成员：完成计数动作，输出计数总数

如果让我来实现的话，有两种实现方式吧，一种是 es5，另一种是 es6，如果有时间和能力，都写吧！！

```javascript
//es5
function Counter(){
  this.c = 0;
}
Counter.prototype.add = function(){
  this.c ++;
}
Counter.prototype.print = function(){
  console.log(this.c);
}

// test
var counter = new Counter()
counter.print(); //0
counter.add();
counter.print(); //1
```

es6 看起来更方便些，但是本质都是一样的：

```javascript
//es6
class Counter{
  constructor(){
    this.id = 0;
  }
  add(){
    this.id ++;
  }
  print(){
    console.log(this.id);
  }
}

// test
var counter = new Counter();
counter.print(); //0
counter.add();
counter.print(); //1
```

### 3

>谈谈你对前端工程化/集成开发环境的理解和实践，借助前端工程化你还可以优化前端开发过程中的哪些环节？

这个问题如果让我来回答，我