---
layout: default
---
# JSON.parse会对key进行排序？
在B/S应用中，服务端返回一个json字符串，前端将json字符串转换为json对象。但是在转换后不保证key的顺序与json字符串中的顺序一致。

``` js
var jsonStr = '{"张三": 90, "李四": 88}'
var jsonObj = JSON.parse(jsonStr)
console.log(jsonObj)
// 输出，key与json字符串一致
{张三: 90, 李四: 88}
```
``` js
var jsonStr = '{"2019": 90, "2018": 88}'
var jsonObj = JSON.parse(jsonStr)
console.log(jsonObj)
```
// 输出，key与json字符串不一致
{2018: 88, 2019: 90}
```