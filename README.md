# 🚀 新舰长上船指南

欢迎来到「求索号」考研舰队！

本指南是专为零基础新舰长准备的 **Git + Obsidian 上船教程**，手把手教你如何 Fork 母舰、本地打开笔记、解决常见问题，并最终通过 Pull Request 贡献你的智慧。

> 💡 **人机协同声明**：求索号不是传统手写笔记，而是一套「PZ 模板 + AI 协同」的方法论示范项目。大部分内容经 AI 结构化后由 Leo 人工审校，你在使用时也应加入自己的理解和批注。

---

## 📋 上船前准备

你需要准备以下三样东西：

1. **GitHub 账号**：用于 Fork 母舰仓库
   - 注册地址：https://github.com/signup
2. **Git**：用于把仓库下载到本地
   - Windows 下载：https://git-scm.com/download/win
   - macOS 下载：`brew install git`
3. **Obsidian**：用于打开和浏览笔记库
   - 下载地址：https://obsidian.md/download

---

## 🎯 三步上船法

### Step 1：Fork 母舰

1. 打开 [github.com/qiusuo-kaoyan/notes](https://github.com/qiusuo-kaoyan/notes)
2. 点击页面右上角的 **Fork** 按钮
3. 选择你自己的 GitHub 账号作为目标
4. 等待几秒，你会看到 `你的用户名/notes` 这个仓库出现

### Step 2：克隆到本地

打开命令行（Windows 按 `Win+R`，输入 `cmd` 回车），执行：

```bash
cd D:\Documents   # 换成你想存放笔记的文件夹
git clone https://github.com/你的用户名/notes.git
```

克隆完成后，你会得到一个 `notes` 文件夹，里面就是全部笔记内容。

### Step 3：用 Obsidian 打开

1. 打开 Obsidian 客户端
2. 点击左下角的 **「打开文件夹作为仓库」**（或英文 "Open folder as vault"）
3. 选择你刚才克隆出来的 `notes` 文件夹
4. Obsidian 会询问是否信任此仓库，点击 **「是」**

---

## 🔌 插件安装（关键！）

Leo 的笔记库依赖多个社区插件才能正常显示看板、模板和数据分析效果。请按以下步骤安装：

### 前置：开启社区插件市场

Obsidian 默认禁用第三方插件。请按以下步骤开启：

1. 打开 Obsidian 左下角 **设置 → 第三方插件**
2. 点击 **关闭安全模式**（或英文 "Turn off safe mode"）
3. 重启 Obsidian
4. 回到 **设置 → 第三方插件 → 社区插件市场 → 浏览**

> ⚠️ 如果找不到"社区插件市场"选项，说明安全模式尚未关闭，请重复步骤 1-2。

---

### 必装插件（不看板就废了）

打开 Obsidian 左下角 **设置 → 第三方插件 → 社区插件市场 → 浏览**，依次搜索并安装：

| 插件名 | 作用 |
|--------|------|
| **Dataview** | 让错题看板、周度复盘自动生成数据报表 |
| **Templater** | 让 PZ 系列模板自动填充日期和元数据 |
| **Kanban** | 让数学/英语任务看板正常显示 |

安装后记得在 **设置 → 第三方插件** 里把每个插件的开关打开。

### 可选插件（提升体验）

以下插件在 `.obsidian/community-plugins.json` 中有记录，但新手可以先不装：

- **Excalidraw** — 画图解和流程图
- **Advanced Canvas** — 增强 Canvas 白板
- **Calendar** — 左侧日历视图
- **Style Settings** + **Blue Topaz 主题** — 调整界面外观

> 💡 **快捷方式**：如果你信任此仓库，Obsidian 有时会提示"检测到社区插件列表，是否一键安装"。如果出现该提示，直接确认即可自动安装列表中所有插件。

---

## ❓ 常见问题 FAQ

### Q1：打开后错题看板是空白的 / 显示 `Dataview: No results to show`

**原因**：Dataview 插件没开，或者文件夹路径和你当前的不匹配。

**解决**：
1. 确认 Dataview 插件已安装并开启
2. **关键**：进入 Dataview 插件的 **设置 → 启用 JavaScript 查询**（英文 "Enable JavaScript Queries"），必须打开，否则数学仪表盘完全无法渲染
2. 确认你的笔记库根目录下有 `1. Math` 文件夹（这是 Dataview 查询的目标）
3. 重启 Obsidian，看板会在启动后重新渲染

### Q2：周复盘里的 DataviewJS 报错 `Invalid unit value`

**原因**：周复盘模板（PZ6）需要 `year` 和 `week_num` 是数字。在模板预览模式下它们是空的，所以会报错。

**解决**：这是正常现象。只有从模板实际创建的周复盘文件才会正常显示数据。

### Q3：任务看板（Kanban）显示异常或无法拖拽

**原因**：Obsidian Kanban 插件没安装。

**解决**：安装 `obsidian-kanban` 插件并开启，然后重新打开看板文件。

### Q4：我只想要数学/专业课笔记，可以删掉其他文件夹吗？

**可以**。`notes` 仓库 Fork 到你名下后就是你的本地副本，你可以自由删除不需要的文件夹（如 `3. English`、`5. 考研日记`）。删除不会影响母舰，也不会影响你后续提交 PR。

### Q5：我可以不改文件夹结构，只往里面加自己的笔记吗？

**可以**。推荐做法是：
1. 保持现有文件夹结构
2. 在 `1. Math` 或对应学科下新建你自己的笔记
3. 使用 `Templates/` 下的 PZ 模板，确保 frontmatter 格式一致

---

## 🙋 如何贡献（提交 PR）

如果你在使用过程中发现了错误、有了更好的解法、或者想补充新的笔记，欢迎通过 Pull Request 反哺母舰。

简单流程：

1. 在本地修改笔记
2. 提交并推送到你 Fork 的仓库
   ```bash
   git add .
   git commit -m "fix: 修正某道数学题的思路"
   git push origin main
   ```
3. 打开 GitHub，进入你的 `notes` 仓库页面
4. 点击 **Contribute → Open pull request**
5. 填写 PR 标题和说明，提交即可

更详细的贡献规范请阅读母舰的 [CONTRIBUTING.md](https://github.com/qiusuo-kaoyan/notes/blob/main/CONTRIBUTING.md)。

---

## 🔗 相关链接

- **知识母舰**：https://github.com/qiusuo-kaoyan/notes
- **星图档案馆**：https://github.com/qiusuo-kaoyan/starlog-archive
- **贡献指南**：https://github.com/qiusuo-kaoyan/notes/blob/main/CONTRIBUTING.md
- **人机协同说明**：https://github.com/qiusuo-kaoyan/notes/blob/main/WORKFLOW.md
- **舰长名录 & Release**：https://github.com/qiusuo-kaoyan/notes/releases

---

*「继往开来，一研为定。」*
