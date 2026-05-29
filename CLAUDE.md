# CLAUDE.md

本文件用于指导 Claude Code 在本仓库中的工作方式。

## 项目简介

这是 **Wentao Hu 的个人学术主页**，基于 Jekyll 搭建，源自开源模板 [`luost26/academic-homepage`](https://github.com/luost26/academic-homepage)，通过 **GitHub Pages** 部署。

- 在线地址（已上线，可直接访问）：<https://wentaohu1208.github.io>
- 部署方式：GitHub Pages 默认的 `pages-build-deployment`（GitHub 内置的 Jekyll 自动构建，无自定义 Actions 工作流）。
- 主分支：`main`

## 工作方式（重要）

网站**已经在线、可正常访问**。Claude 的职责是：

1. **只在本地修改**仓库中的文件（内容、模板、样式等）；
2. 修改完成后，将改动 **commit 到本地并 push 到远程 `main` 分支**；
3. push 后 GitHub Pages 会自动重新构建部署，通常几分钟内线上生效，无需手动操作。

> 在此之前，仓库主人都是手动改动并推送；现在改为由 Claude 在本地完成修改后提交。

## 目录结构

| 路径 | 用途 |
|------|------|
| `_config.yml` | Jekyll 站点全局配置（不常改，改后需重启本地服务） |
| `_data/` | 数据文件（如 `profile.yml`，个人信息/经历等高频修改处） |
| `_includes/` | 可复用模板片段（如 `profile_card.html`、`experience_card.html`） |
| `_layouts/` | 页面布局模板 |
| `_publications/` | 论文集合（collection） |
| `_news/` | 新闻动态集合（collection） |
| `_showcase/` | 展示内容集合（collection） |
| `assets/` | 图片、CSS、JS 等静态资源 |
| `index.html` / `publications.html` / `showcase.html` / `404.html` | 各页面入口 |

> 最常更新的内容通常位于 `_data/` 与各 collection 目录（`_publications/`、`_news/`、`_showcase/`）。

## 本地预览（可选）

```bash
bundle exec jekyll serve
```

然后访问终端显示的本地地址即可预览改动效果。

## 约定

- **提交规范**：使用 Conventional Commits（如 `feat:`、`fix:`、`docs:`、`chore:`）。
- **不提交任何密钥/令牌**：本仓库为公开仓库，且文件可能被 Jekyll 复制到线上站点。
- **修改前先了解上下文**：编辑模板或样式前，先查看 `_includes/`、`_layouts/` 中对应文件，保持风格一致。
