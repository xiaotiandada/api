# Api

Easy-mock 模拟的接口，后期我会专门开一个链接放置接口提供测试， 欢迎 PR~

## 分页接口

> offset 页数
> limit 数量

```js
{
  "code": 200,
  "count": 1000,
  "_req": function({
    _req
  }) {
    return _req.query
  },
  "data": function({
    _req
  }) {
    let arr = []
    for (var i = 0; i < 1000; i++) {
      arr.push({
        "id": `10000-${i}`,
        "username": `user-${i}`,
        "content": `问答内容问答内容问答内容问答内容问答内容问答内容问答内容问答内容问答内容问答内容问答内容问答内容-${i}`,
        "status": "待审核"
      })
    }

    return arr.slice((_req.query.offset - 1) * _req.query.limit, (_req.query.offset) * _req.query.limit)
  }
}
```
