# Gatsby-Tutorial
学习Gatsby的历程


## JavaScript
### 变量
var，全局
let、const，{}块作用域
const一般不可以修改，除非它是一个对象，并提供了修改自身内容的方法

### 箭头函数
通常匿名函数定义
```javascript
// 通过函数表达式来定义
const myFunction = function(){

}
```
箭头函数定义
```javascript
const myFunction = () => {

}
this关键字
- 上下文
- JavaScript模式：strict模式

> The this scope with arrow functions is inherited from the execution context. An arrow function does not bind this at all, so its value will be looked up in the call stack, so in this code car.fullName() will not work, and will return the string "undefined undefined":

箭头函数不适合作为对象的方法

### 使用扩展运算符处理对象和数组
```javascript
const a = [1, 2, 3]
const b = [...a, 4, 5, 6]


```
使用扩展运算符来简化函数参数

### 对象和数组的解构，Destructuring
将属性/值，从对象/数组中取出，赋值给其他变量

### 模版字符串
```javascript
const a_string = `something`

```
多行字符串
```javascript
const string = 
    'first part \
second part'

// 另外一种表达方式
const string = 'first line\n' + 'second line'

// 使用模版字符串
const string = `Hey
this

string
is awesome!`


```

插值，模版赋值。就是shell语法
```javascript
// 通常可以使用$来解析变量
const myVariable = 'test'
const string = `something ${myVariable}` //something test

const string = `something ${1 + 2 + 3}`
const string2 = `something ${doSomething() ? 'x' : 'y'}`

```

模版标签
```javascript
// 在styled compocomponents中，使用模版标签定义CSS
const Button = styled.button`
  font-size: 1.5em;
  background-color: black;
  color: white;
`
```

### 异步编程与回调函数
https://flaviocopes.com/javascript-callbacks/

javascript默认是同步的，并且是单线程的，这意味着程序不能创建新线程并且同时运行。

但是浏览器提供了一系列的api去处理类似`onClick`等的事件
> More recently, Node.js introduced a non-blocking I/O environment to extend this concept to file access, network calls and so on.

回调函数，事件触发
例如：
```javascript
document.getElementById('button').addEventListener('click', () => {
    // item click

})

// eg.2
setTimeout(() => {
    // run after 2 second
}, 2000)

// eg.3
const xhr = new XMLHttpClient()
xhr.onreadystatechage = () => {
    if(xhr.readyState == 4){
        xhr.status == 200? console.log(xhr.responseText): console.error('error')
    }

}
xhr.open('GET', 'http://baidu.com')
xhr.send()

```


error-first callbacks
```javascript

fs.readFile('/file.json', (err, data) => {
  if (err !== null) {
    //handle error
    console.log(err)
    return
  }

  //no errors, process data
  console.log(data)
})
```

回调函数如果有多层嵌套，会十分复杂
从ES6开始，提供了`异步代码`的支持
- Promises
- Asynchronous/Await

### ES模块化
> ES Modules is the ECMAScript standard for working with modules

浏览器没有一个模块系统，直到ES6
> Modules are very cool, because they let you encapsulate all sorts of functionality, and expose this functionality to other JavaScript files, as libraries.

模块允许我们去封装功能，并作为库暴露给其他文件

> A module is a JavaScript file that exports one or more values (objects, functions or variables), using the export keyword. For example, this module exports a function that returns a string uppercase:

模块是一个javascript文件，可以导出变量（对象、函数、变量）

```javascript
// 导入模块
import package from 'module-name'

// CommonJS的方式
const package = require('module-name')

// 匿名函数可以作为默认导出
export default str => str.toUppperCase()


// HTML可以通过<script>标签
<script type="module" src="index.js"></script>

```


## React
开始React之路
