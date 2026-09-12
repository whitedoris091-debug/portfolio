# AGENTS.md

# 项目上下文

白幸平个人作品集网站 — 亮色白底+蓝色主强调+弥散雾蓝光晕+毛玻璃+4页切换架构。

### 版本技术栈

- **模式**：原生极简 (native-static)
- **语言**：纯 HTML / CSS / JS（单文件 index.html）
- **字体**：Google Fonts CDN — Space Grotesk / Inter / JetBrains Mono / Noto Sans SC
- **路由**：Hash 路由 (#/project/1-6)，4 页切换 (Home / About / Portfolio / Contact)，慧眼导航(id=1)有专用详情页 showSmartGlassesDetail

## 目录结构

```
├── index.html      # 唯一入口文件，包含所有 CSS 和 JS
├── .coze           # 构建运行配置
├── DESIGN.md       # 设计规范
└── AGENTS.md       # 本文件
```

## 包管理规范

无包管理器，纯静态文件。

## 开发规范

### 配色（严格）

- 页面背景 `#F8FAFD`（极浅蓝灰白），禁止暗色/纯黑背景
- 卡片 `rgba(255,255,255,0.7)` + `backdrop-filter: blur(16px) saturate(1.2)`
- 强调色 `#16689F`（湖蓝，全站核心），hover `#1E7AB5`
- 文字主色 `#1A2332`（深蓝黑），辅色 `#6B7A8D`（蓝灰）
- 撞色 `#bf0a2d`（酒红，仅"进行中"标签等极少量点缀）
- 暖色 `#fbec8e`（鹅黄，仅装饰光晕）
- 弥散光晕在亮色底上 opacity 0.08-0.12，blur 120px

### 交互模式

- 页面切换：淡入淡出 300ms
- 卡片 hover：border 变湖蓝 + translateY(-4px) + 阴影增强 + 视频播放
- 详情页：hash 路由，右侧滑入 500ms
- Lightbox：点击截图全屏放大（亮色遮罩）
- 搜索：实时筛选卡片（opacity 0.2 + blur 2px）

### 视频交互

- 卡片封面区 img z-index:2 遮挡 video z-index:1
- hover 时 img opacity→0，video 播放
- 移动端点击切换播放/暂停
- video preload="none"

## 构建与测试

```bash
# 开发服务器由 .coze 配置管理，使用 python http.server
# 无需构建步骤
```
