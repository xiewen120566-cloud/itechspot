这个目录是纯静态站点（不依赖 Next.js 运行时）。

入口：
- 333/index.html（默认英文，可用 ?lang=ja-JP 切到日语）

依赖的数据与资源（从项目根目录读取）：
- ../data/en-US 与 ../data/ja-JP
- ../messages/en-US.json 与 ../messages/ja-JP.json
- 333/public/static（logo/favicon 等）

复制 public 到 333：
- 在 e:\jia\123\claw 运行：node .\333\copy-public.cjs

为什么直接双击打开 index.html 看不到东西：
- 浏览器在 file:// 模式下会限制 fetch 读取本地 json，所以页面拿不到数据就会空白

本地预览（推荐）：
- 在 e:\jia\123\claw 运行：node .\333\serve.cjs
- 然后访问：/333/index.html

离线打开（无需本地服务器）：
- 先在 e:\jia\123\claw 运行：node .\333\build-standalone.cjs
- 然后直接双击打开：333/index.html（会从 333/generated 读取内置数据）
