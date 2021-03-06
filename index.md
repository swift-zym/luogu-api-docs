# 洛谷 API 文档

不方便直接列出的类型定义在 [luogu-api.d.ts](https://github.com/sjx233/luogu-api-docs/blob/master/luogu-api.d.ts).

* [题目](problems.md)
* [题单](problem-sets.md)
* [比赛](contests.md)
* [记录](records.md)
* [讨论](discussions.md)
* [动态](activities.md)
* [用户](users.md)
* [团队](teams.md)
* [私信](chat.md)
* [主题](themes.md)
* [图片](images.md)
* [IDE](ide.md)
* [剪贴板](pastes.md)
* [博客](blog.md)
* [身份验证](auth.md)
* [杂项](misc.md)

## 范例

### `GET` 请求

```js
fetch("https://www.luogu.com.cn/problem/list?type=P&keyword=%E3%80%90%E6%A8%A1%E6%9D%BF%E3%80%91&_contentOnly");
```

### `POST` 请求

**注**: 所有非 `GET` 请求都需要包含[名为 `X-CSRF-Token` 的请求头字段](misc.md#获取-csrf-token)。

**注**: 所有非 `GET` 请求都需要包含名为 `Referer` 的请求头字段,表示当前请求的来源。

```js
fetch("https://www.luogu.com.cn/api/chat/new", {
  headers: {
    "Content-Type": "application/json",
    "X-CSRF-Token": token,
    "Referer": "https://www.luogu.com.cn/discuss/lists"
  },
  body: JSON.stringify({
    user: 206953,
    content: "Hi"
  }),
  method: "POST"
});
```
