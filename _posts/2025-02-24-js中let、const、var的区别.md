---
layout: post
title: js中let、const、var的区别
date: 2025-02-24
tags: js笔记
---
# let、const、var的区别

## 1. 作用域

* ***var***函数作用域 （ 在函数内部声明的变量尽在函数内部有效）。
* ***let/const*** 块级作用域 （在 **{}** 内声明的变量仅在块内有用，如 if、for 等 。

```javascript
function varExample() {
  if (true) {
    var a = 10; // 函数作用域
    let b = 20; // 块级作用域
  }
  console.log(a); // 10（可访问）
  console.log(b); // ReferenceError: b未定义
}
varExample();
```

## 2. 变量提升

* ***var*** ： 变量声明会提升到作用域顶部  , 但是赋值不会
```javascript
console.log(x) ; //  10
console.log(window.x) ; // 10
var x = 10 ;  // undefined
```
* ***let、const***  声明前访问报错

## 3. 可变性

* ***const*** ：定义常量，定义后不可再次修改 ，声明时必须初始化
```javascript
const PI = 3.14 ;
PI = 1.1 ; // 报错
```

* ***var、let*** ： 可重复修改，修改后覆盖原本的值


## 4. 全局作用域行为

* ***var*** 定义全局变量时，该变量会被绑定到window对象

## 5. 使用建议

* 优先 const ， 减少变量的修改
* 其次 let 
* 最后 var 尽量避免泄露等意外情况的发生