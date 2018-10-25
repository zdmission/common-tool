## 一、描述
> 封装了常用的处理方法，比如存储cookie，storage，日期格式化，小数点等等

## 二、安装
```
npm/cnpm install common-tool
```

## 三、使用示例
``` js
import {trim,cookie,Math_add,Math_sub,Math_mul,Math_div,goUrl,getPara,storage,delStorage,isJson,remFn,formatThousandUpdate,formatThousand,formatTime,formatSecond,toGoOrigin,paramSerialization,utils,isEmptyObject,isMobile,isIDCard,isHasChinese} from 'common-tool'

/**
 * 去空格trim
 * */
trim(' test zdmission lc') // 结果 testzdmissionlc

/**
 * cookie的存储获取
 * */
// 存储
cookie('test','测试数据')
// 获取
cookie('test')

/**
 * Math_add 算术运算-加法
 * */
Math_add(5,2) //结果 7

/**
 * Math_sub 算术运算-减法
 * */
Math_sub(5,2) //结果 3

/**
 * Math_mul 算术运算-乘法
 * */
Math_mul(5,2) //结果 10

/**
 * Math_div 算术运算-除法
 * */
Math_div(5,2) //结果 2.5

/**
 * goUrl 页面跳转
 * */
goUrl('http://zdmission.cn')

/**
 * getPara 获取url中的某个参数
 * */
// http://zdmission.cn/pages/viewpage.action?pageId=17367967
getPara('pageId') // 结果 17367967

/*获取系统时间
 *参数类型
 *time:返回时间戳
 *默认返回：yyyy-mm-dd:年月日
 */
getSysTime('time') // 1538107018311
getSysTime() // "2018-09-28"

/**
 * storage 本地存储-获取/增加/修改 value值为字符串或者json对象
 * */
// 存储
storage('test','test') // test的值为test
// 修改
storage('test','test1') // test的值为test1
// 获取
storage('test') // test1

/**
 * delStorage 删除本地存储
 * */
// 删除某一个值
delStorage('test')
// 删除全部值
delStorage()

/**
 * isJson 判断字符串是否是json格式
 * */
isJson(JSON.stringify({name: 'zdmission'})) // true
isJson('zdmission') // false

/**
 * remFn rem布局设置函数
 * */
remFn(56) // html的font-size: 56px;

/**
 * formatThousandUpdate 千分位加小数点
 * @param {string,number} num 表示需要转换的数据
 * @param {number} isFixed 表示保留的小数位,传入值是小数,默认情况是原数输出
 */
formatThousandUpdate(52) // 52
formatThousandUpdate(52.567) // 52.567
formatThousandUpdate(52.567,2) // 52.57 四舍五入
formatThousandUpdate(5256.56, 2) // 5,256.57

/**
 * formatThousand 千分位加小数点
 * @param {number} num 表示需要转换的数据
 * @param {number} isFixed 小数的位数,默认为2位小数
 * */
formatThousand(52) // 52.00 默认是两位小数
formatThousand(52000,2) // 52,000.00

/**
 * formatTime 时间戳转换日期格式，接口返回的是毫秒
 * @param {number} value unix时间戳
 * @param {string} type 年月日之间的隔开方式，比如'/'、'-'
 * @return {string}
 */ 
formatTime(1538115885233) // 2018-09-28
formatTime(1538115885233,'/') // 2018/09/28

/**
 * formatSecond 时间戳转换成年月日时分秒，形如 2018-04-16 15:13:14
 * @param {number} value unix时间戳
 * @return {string}
 * */
formatSecond(1538115885233) // "2018-09-28 14:24:45"


/**
 * toGoOrigin 记录位置，切页面后回来滚动到上一次滚动的位置
 * */
toGoOrigin()

/**
 * paramSerialization 参数序列化
 * @param {object} data 参数是json对象
 * @return {string}
 */
paramSerialization({name:'jianlc',age: 3}) // name=jianlc&age=3

/**
 * utils 对象增加方法，判断数据类型
 * @param {function,object,string,undefined} value
 * @return {boolean}
 * */
utils.isFunction(a)
utils.isObject(a)
utils.isString(a)
utils.isUndefined(a)

/**
 * isEmptyObject 判断是够是空对象
 * @param {object} obj 传入对象
 * @return {boolean}
 * */
isEmptyObject({}) // false
isEmptyObject({name:'jianlc'}) // true

/**
 *
 * isMobile 正则判断是否是手机号
 * @param {String} str
 * @returns {Boolean}
 */
isMobile('zdmission') // false
isMobile('1765635456') // true

/**
 *
 * isIDCard 正则判定身份证号是否合法
 * @param {String} str
 * @returns {Boolean}
 */
isIDCard('zdmission') // false
isIDCard('11010119900307969X') // true

/**
 *
 * isHasChinese 是否含有中文字符
 * @param {String} str
 * @returns {Boolean}
 */
isHasChinese('zdmission') // true

```

## 四、版本说明
  
### 1.0.0版本
- 1.bug修复
- 2.增加功能
    - 增加常用的工具方法