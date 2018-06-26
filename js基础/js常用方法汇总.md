4## js基础常用方法一览
- length方法可以获取字符串和数组的长度
  + `console.log('天赐桃花源，桃香满天下'.length) // 11 `
  + `console.log(['天下隆中对', '传奇襄阳城'].length) // 2 `
- 检测简单的数据类型的方法
  + typeof方法用于检测简单的数据类型如`typeof 12`
  + instanceof的实例方法检测如`[] instanceof Array // true`
  + `arr.constructor == Array`判断arr的构造函数是否为数组，如果是则arr是数组
  + `Array.isArray([])`判断是否是数组
  + 精确判断数据类型`Object.prototype.toString.call(arr)`
- 数据类型之间的转化方法
  + toString()转换为字符串
  + parseInt()转换为整型
  + parseFloat()把字符串转换成浮点数
  + 取正转换为数值型`var str = '500';console.log(+str);`
  + Boolean()转换为布尔。2句口诀
  + 用取反隐式转换如`var str = '襄阳卡五星'; console.log(!str); // false`
- Math方法
  + Math.max(42,52)取2个值中的最大值 52
  + Math.min(42,33)取2个值中的最小值 33
  + Math.max.apply(null,arr) 取数组中的最大值
  + Math.min.apply(null,arr) 取数组中的最小值
  + Math.PI             // 圆周
  + Math.random()       // 生成随机数
  + Math.floor()/Math.ceil()   // 向下取整/向上取整
  + Math.round()        // 取整，四舍五入`注意``Math.round(-1.5) // -1`
  + Math.abs()          // 绝对值
  + Math.max()/Math.min()    // 求最大和最小值
  + Math.sin()/Math.cos()    // 正弦/余弦
- Date对象相关
  + new Date() 来创建日期实例(对象)
  + getTime()     // 返回毫秒数和valueOf()结果一样，valueOf()内部调用的getTime()
  + getMilliseconds() 
  + getSeconds()  // 返回0-59
  + getMinutes()  // 返回0-59
  + getHours()    // 返回0-23
  + getDay()      // 返回星期几 0周日   6周6
  + getDate()     // 返回当前月的第几天
  + getMonth()    // 返回月份，***从0开始***
  + getFullYear() //返回4位的年份  如 2016
  - toDateString()
  - toTimeString()
  - toLocaleDateString()
  - toLocaleTimeString()
- console对象的方法
  + console.log()方法用于在控制台输出信息。它可以接受多个参数，逗号分隔
  + console.warn()方法用于输出黄色警告信息
  + console.error()方法用于输出红色错误信息
  + console.dir()方法用来对一个对象进行检查，并以易于阅读和打印的格式显示
- 数组的常用方法
  ```javascript
  push()      // 往数组中添加，并返回数组的长度
  pop()       // 删除数组中的最后一项，并返回删除的那一项
  shift()     // 取出数组中的第一个元素，修改length属性
  unshift()   // 在数组最前面插入项，返回数组的长度
  // 3 排序方法
  reverse() //翻转数组
  sort();   //即使是数组sort也是根据字符，从小到大排序
  // 带参数的sort是如何实现的？
  // 4 操作方法
  concat()    //把参数拼接到当前数组
  slice()     //从当前数组中截取一个新的数组，不影响原来的数组，参数start从0开始,end从1开始
  splice()    //删除或替换当前数组的某些项目，参数start, deleteCount, options(要替换的项目)
  // 5 位置方法
  indexOf()、lastIndexOf()   //如果没找到返回-1
  // 6 迭代方法 不会修改原数组(可选)  html5
  every()、filter()、forEach()、map()、some()
  // 7 方法将数组的所有元素连接到一个字符串中。
  join()
  // 8 将字符串分割为数组
  split()
  ```

- 清空数组
  ```javascript
  // 方式1 推荐 
  arr = [];
  // 方式2 
  arr.length = 0;
  // 方式3
  arr.splice(0, arr.length);
  // 补充 splice() 方法向/从数组中添加/删除项目，然后返回被删除的项目
  // 1. 语法： arrayObject.splice(index,howmany,item1,.....,itemX)
  // 1.1 index 必需。整数，规定添加/删除项目的位置，使用负数可从数组结尾处规定位置。
  // 1.2 howmany 必需。要删除的项目数量。如果设置为 0，则不会删除项目。
  // 1.3 item1, ..., itemX可选。向数组添加的新项目。
  // 1.4 具体使用案例
  var arr = ["张三","李四","王五","赵六","H5","CSS3"]
  document.write(arr + "<br />")
  arr.splice(2,3,"Itcast")
  document.write(arr)
  ```

- 字符串的方法介绍
  ```
  // 1 字符方法
  charAt()        //获取指定位置处字符
  charCodeAt()    //获取指定位置处字符的ASCII码
  str[0]          //HTML5，IE8+支持 和charAt()等效
  // 2 字符串操作方法
  concat()        //拼接字符串，等效于+，+更常用
  slice()         //从start位置开始，截取到end位置，end取不到
  substring()     //从start位置开始，截取到end位置，  end取不到
  substr()        //从start位置开始，截取length个字符
  三者区别[三者区别](https://www.cnblogs.com/littledu/archive/2011/04/18/2019475.html)
  // 3 位置方法
  indexOf()       //返回指定内容在元字符串中的位置
  lastIndexOf()   //从后往前找，只找第一个匹配的
  // 4 去除空白
  trim()          //只能去除字符串前后的空白
  // 5 大小写转换方法
  to(Locale)UpperCase()   //转换大写
  to(Locale)LowerCase()   //转换小写
  // 6 其他
  replace(a, b) 用法str.replace(a, b) 在str中用b替换a
  split()
  ```