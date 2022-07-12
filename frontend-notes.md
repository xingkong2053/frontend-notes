# 前端
## javacript
### 作用域和变量提升
### es6语法
- var, let, const
  - var/let 区别
    - var es5, let es6
    - 变量提升
    - 块级作用域
    - 重复声明
    - 暂时性死区
  - let/const 区别
    - const声明时必须要赋初值
    - let能够重新赋值, const不能重新赋值
- 解构赋值
  - 数组解构赋值
  - 对象解构赋值
  - 字符串解构赋值
- 字符串拓展
  - 字符的Unicode表示法
  - `at()`
  - `normalize()`
  - `includes()`
  - `startsWith(), endsWith()`
  - `repeat()`
  - `padStart(), padEnd()`
  - `repeat()`
  - 模板字符串
  - 标签模板
  - `String.raw()`
- 正则拓展
- 数值拓展
- 箭头函数
  - 箭头函数和普通函数的区别: 箭头函数无this也无arguments对象
- spread和rest传参
- 数组方法拓展
  - `Array.from()`
  - `Array.of()`
  - `.copyWithin()`
  - `.find(), .findIndex()`
  - `.fill()`
  - `.entries(), .keys(), .values()`
  - `.includes()`
- 对象方法拓展
  - `Object.is()`
  - `Object.assign()`
  - 属性可枚举性
  - 属性的遍历
  - `Object.keys(), Object.values(), OBject.entries`
  - 对象拓展运算符
- Promise
  - 实例方法
    - `.then`
    - `.catch`
    - `.finally`
  - 静态方法
    - `Promise.resolve`
    - `Promise.reject`
  - 期约合成
    - `Promise.all`
    - `Promise.race`
  - 如何实现一个Promise
- async/await
- Symbol基本类型
- Set和Map数据结构
- Proxy
- Reflect
- iterator和for...of循环
- Class
- 模块
### 事件循环
## css
### bfc
- 块级格式化上下文
## html
## HTTP
### OSI模型
### TCP/IP
- 三次握手四次挥手
- UDP
- TCP和UDP区别
### HTTP报文结构
### HTTP状态码
- 2xx
- 3xx
- 4xx
- 5xx
### HTTP头
- 通用头部
- 请求头部
- 响应头部
- 实体头部
### HTTP缓存
- [MDN | HTTP缓存](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Caching)
- 缓存种类
  - 浏览器缓存
  - 代理缓存
- 缓存控制
  - `Cache-Control`头
    - no-store
      - 不做缓存, 每次发送请求都会下载完整内容
    - no-cache
      - 每次发送请求都会向服务器验证缓存有效期, 若缓存未过期(status code: 304)则使用本地副本
    - private
      - 响应只能应用于浏览器私有缓存中, 中间人不能缓存此响应
    - public
      - 响应可以被任何中间人(如中间代理, CDN等)缓存
    - `max-age=<seconds>`
      - 表示资源能够被缓存的最大时间
    - must-revalidate
      - 缓存在考虑使用一个陈旧的资源时, 必须先验证它的状态, 已过期的缓存不能被使用
  - `pragma`头
    - 和cache-control: no-cache相同, 通常用于向后兼容HTTP/1.0客户端
  - `Vary`头
    - Vary用于指定更加细粒度的缓存, 如`Vary: Accept-Language`会对同一个请求但不同语言的响应分别缓存, `Vary: User-Agent`则对不同的客户端发起的请求分别缓存

- 新鲜度
  - 由于HTTP是C/S模式的协议, 服务器更新一个资源时, 不可能通知客户端直接更新缓存
  - 所以双方必须为该资源约定一个过期时间, 在该过期时间之前，该资源（缓存副本）就是新鲜的，当过了过期时间后，该资源（缓存副本）则变为陈旧的
  - 缓存检索到已有一个对应的**陈旧资源**（缓存副本），则缓存会先将此请求附加一个 `If-None-Match` 头，然后发给目标服务器，以此来检查该资源副本是否是依然还是算新鲜的，若服务器返回了 `304 (Not Modified)`（该响应不会有带有实体信息），则表示此资源副本是`新鲜`的
  - 若服务器通过 `If-None-Match` 或 `If-Modified-Since` 判断后发现已过期，那么会带有该资源的`实体内容`返回
- 版本号机制
  - 不频繁更新的文件会使用特定的命名方式：在 URL 后面（通常是文件名后面）会加上版本号
  - 好处: 同时更新两个缓存资源不会造成部分缓存先更新而引起新旧文件内容不一致
  - 对于相互依赖的两个CSS和JS文件, 避免这种不一致是非常重要的
  - 不一定是正式的版本号, 也有可能是hash或者时间戳
- Expires和max-age
  - HTTP 1.0 -> Expires
    - 缺点: 当系统时间不正确时会出现问题
  - HTTP 1.1 -> Cache-control: max-age
- 缓存验证
  - `If-Modified-Since`
  - `ETag/If-None-Match`
  - Force Revalidation
### 跨源资源共享(CORS)
- TODO
## Vue

## React