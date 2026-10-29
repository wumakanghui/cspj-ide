# 算法工坊 · CSP-J 在线 C++ IDE

一个面向 CSP-J / 洛谷算法练习的中文在线 C++ 编辑器。纯静态页面，无需 Node.js、无需在机房安装软件，部署在 GitHub Pages 后即可通过固定网址访问。

## 功能

- C++ 语法高亮、行号、括号匹配和自动补全括号（由 CodeMirror CDN 提供）
- GNU C++17 / C++14 / C++20 / C++11 选择；自动从 Wandbox 读取可用 GCC 编译器版本
- 标准输入、程序输出、编译信息分栏显示
- `Ctrl + Enter` 编译运行，`Ctrl + S` 导出 `main.cpp`
- 基础输入输出、DFS、BFS、二分查找、双指针、并查集模板
- 自动把代码和标准输入保存到当前浏览器；可切换明暗主题
- 下载当前代码为 `main.cpp`

## 重要说明

1. 这是静态网页，编译/运行请求发送到公开的 Wandbox API：`https://wandbox.org/api/compile.json`，因此不需要自行部署编译服务器或保存 API 密钥。
2. 代码会发给第三方编译服务执行。不要输入密码、令牌或其他敏感内容。
3. 这是用于个人学习的轻量版本，不是正式 OJ。公共编译 API 可能限流、维护或暂时不可用；它也不保证与洛谷/正式 CSP 评测环境的编译器和资源限制完全一致。
4. 网页加载 CodeMirror 的语法高亮资源也需要访问 CDN。如果 CDN 无法访问，页面仍会保留基础文本编辑区；若机房同时屏蔽 Wandbox，则不能通过此页面在线编译。
5. 代码和输入只保存在当前浏览器的本地存储中，不会自动同步到其他电脑。重要代码请点击“导出代码”备份。

## 部署到 GitHub Pages（推荐）

整个项目只有静态文件，不需要构建命令。

1. 登录 GitHub，创建一个新仓库，例如 `cspj-ide`。用于 GitHub Pages 的仓库建议设为 Public。
2. 解压此项目，把 `index.html` 和 `README.md` 上传到仓库根目录（不要再套一层同名文件夹）。在 GitHub 仓库页点击 **Add file → Upload files**，上传后点击 **Commit changes**。
3. 打开仓库的 **Settings → Pages**。
4. 在 **Build and deployment** 中选择 **Deploy from a branch**；Branch 选择 `main`，目录选择 `/(root)`，点击 **Save**。
5. 等待 GitHub Pages 完成首次发布。固定网址会是：

   `https://你的GitHub用户名.github.io/cspj-ide/`

   把“你的GitHub用户名”替换成账号名。之后再次上传或提交文件，GitHub Pages 会更新同一个网址。

## 部署到 Netlify（备选）

也可登录 Netlify，创建一个新的静态站点并上传包含 `index.html` 的项目目录。站点会得到一个 `*.netlify.app` 地址；在站点设置中可以修改站点子域名。Netlify 的界面可能随产品更新调整，以当前控制台显示为准。

## 如何在机房使用

1. 浏览器打开部署后的固定网址。
2. 在左侧代码区编写程序，右侧“标准输入”填写 `cin` 要读取的数据。
3. 点击“运行代码”，或按 `Ctrl + Enter`。
4. 正常输出看“运行结果”；编译错误或警告看“编译信息”。
5. 退出前点击“导出代码”保存为 `main.cpp`，避免因清理浏览器数据而丢失。

## 本地预览

可以直接双击 `index.html` 预览界面；不过某些浏览器的本地文件安全策略可能影响网络请求。部署在 HTTPS 静态站点上更可靠。
