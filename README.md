# moment

日期处理类库

- 中文网：http://momentjs.cn/docs/

- 官网：https://momentjs.com/docs/

## Node中使用

- 下载：```npm i moment```
  

- 引入

```js
var moment = require('moment');
```

- 更多环境，参考官网

## 解析

### moment()

要获取当前的日期和时间，只需调用不带参数的 moment() 即可。

函数参数在未传入时默认为 undefined。 Moment 会将 moment(undefined) 视作 moment()。

```js
var moment = require('moment');

var now = moment();
// var now = moment(undefined);

console.log(now); //Moment<2020-12-10T10:41:43+08:00>
```

### moment(String);

```js
var now = moment("1995-12-25");

console.log(now);//Moment<1995-12-25T00:00:00+08:00>
```

```js
var test = moment("12-25-1995", "MM-DD-YYYY");

console.log(test);//Moment<1995-12-25T00:00:00+08:00>
```

### moment(Object)

```js
var test1 = moment({ years:'2010', months:'3', date:'5', hours:'15', minutes:'10', seconds:'3', milliseconds:'123'});  // 从 2.11.0 开始。
console.log(test1);//Moment<2010-04-05T15:10:03+08:00>

```

### moment(Number) 1.0.0

与 new Date(Number) 类似，可以通过传入一个整数值来创建 moment，该整数值表示自 Unix 纪元（1970 年 1 月 1 日 12AM UTC）以来的毫秒数。

```js
var day = moment(1318781876406);
console.log(day);//Moment<2011-10-17T00:17:56+08:00>
```

## 取值和赋值

Moment.js 使用重载的 getter 和 setter 方法。 此模式类似与其在 jQuery 中的使用。

不带参数调用这些方法会作为 getter，而带参数调用则会作为 setter。

从 2.0.0 版本开始，单数和复数的方法名称都会存在。

```js
// 取值
moment().seconds();
// 赋值
moment().seconds(25);

var test = moment().seconds(25);
console.log(test);// //Moment<2020-12-10T11:15:25+08:00>

var s = moment().year(2021).month(1).date(1);
console.log(s);//Moment<2021-02-01T11:18:33+08:00>
```
- day() 1.3.0+

获取或设置星期几。

此方法可用于设置星期几，其中星期日为 0、星期六为 6。

如果给定的值是 0 到 6，则结果的日期将会在当前（星期日至星期六）的星期。

如果超出范围，则它将会冒泡到其他星期。

```js
//当前日期为2020-12-10 星期四  Moment<2020-12-10T10:41:43+08:00>

// 当前时间的上个星期日的日期 上周日的日期 2020-12-06 星期日
var s = moment().day(0);
console.log(s);//Moment<2020-12-06T11:20:39+08:00>

// 这周日的日期 2020-12-13 星期日
var s = moment().day(7);
console.log(s);//Moment<2020-12-13T11:26:08+08:00>
```

