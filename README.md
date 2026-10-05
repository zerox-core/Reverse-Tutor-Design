# Reverse-Tutor-Design（设计方向交接仓）

Reverse Tutor Android 的**设计方向代码**单独管理仓，用于交接给负责前端设计增改的云端 agent。

## 分工约定（2026-10-05 用户拍板）

- **本仓 = 设计方向**：用户反馈的界面/交互设计问题，由「本地开发搭档」登记到 `ISSUES.md`（只标注问题，不写设计方向），其他云端 agent 在此认领并进行前端设计增改。
- **功能缺陷不在本仓**：功能性问题仍回原仓库 [Reverse-Tutor](https://github.com/zhuxice-ctrl/Reverse-Tutor)（分支 `Android`），由本地开发搭档直接修复。

## 目录

- `frontend/` — UI 层代码快照（Jetpack Compose，Kotlin）。目录结构保留源仓库 `mobile-native/` 之后的相对路径，按模块分：
  - `core/design/` — 设计令牌（FormalDesign 体系：颜色/字号/间距/圆角）
  - `app/theme/`、`app/ui/` — 主题与 Rt* 设计系统组件
  - `app/shell/` — 工作区外壳与各路由屏
  - `feature/chat/` — 聊天/创建流程/会话设置等界面
  - `feature/memory/` — 图谱/周报/上下文中枢界面
  - `feature/settings/`、`feature/sources/` — 设置与资料界面
- `ISSUES.md` — 设计问题标注清单（登记规范见文件头）。

## 快照基线

- 源：`Reverse-Tutor` 分支 `Android`，HEAD = 1285674，快照日期 2026-10-05。
- 快照取自**工作树**，包含尚未提交的 R99（滚动/联网搜索/上下文/追问调优）与 R100（搜索默认开 + 创建流程状态机 + 孵化草案卡/学习流程图卡）改动。
- 本快照**不可构建**（仅 UI 层 .kt 文件，无 gradle 工程/资源/依赖）。改设计时以原仓库相同相对路径的文件为准进行修改与回写，本仓文件用于阅读、标注与交接。

## 同步方式

用户反馈设计问题 → 本地开发搭档更新 `frontend/` 快照与 `ISSUES.md` → 设计 agent 认领条目 → 改动落回原仓库（由本地开发搭档执行构建/测试/装机验证）。
