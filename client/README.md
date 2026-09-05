# FrameForge AI 前端

本目录是 FrameForge AI 的 Vue 3 前端，提供本地视频分片上传、断点续传、任务列表、分析进度、证据报告、继续追问和用户认证界面。

## 本地启动

推荐使用 Node.js 22 或更高版本。

```bash
cd client
npm install
npm run dev
```

页面默认运行在 `http://localhost:5173`，后端 API 默认地址为 `http://localhost:9090`。页面支持本地视频上传和 BV 号导入：BV 导入会调用 B 站公开接口并由后端使用 `yt-dlp` 下载，受平台风控或外部网络影响时可能失败，此时可改用本地视频上传。需要修改 API 地址时，可设置环境变量：

```bash
VITE_API_BASE_URL=http://localhost:9090
```

## 演示模式

访问 `http://localhost:5173/?demo` 可直接查看内置的视频分析结果，不依赖后端、数据库或模型密钥。

## 构建检查

```bash
npm run build
```

前端基于 Vue 3、Vite 和 Marked 开发。界面渲染模型返回的 Markdown 前会过滤不受支持的标签和属性，避免直接执行模型输出中的危险 HTML。
 
