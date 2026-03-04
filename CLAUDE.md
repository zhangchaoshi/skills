# CLAUDE.md

此文件为 Claude Code (claude.ai/code) 在此仓库中工作提供指导。

**重要：在此仓库中工作时，请使用中文回答用户的问题。**

## 仓库概述

这是个人收集的 Claude Code 技能集合，以 Markdown 文件形式存储。技能是可复用、具有上下文感知能力的提示，用于指导 Claude Code 处理特定任务。


## 仓库结构

```
Skill-Hub/
├── skills/                   # 所有技能定义
│   └── <技能名称>/           # 单个技能目录
│       └── SKILL.md          # 技能定义文件
└── .claude-plugin/
    └── marketplace.json      # Claude Code 插件元数据
```

## 添加新技能

1. 在 `skills/` 下创建一个新目录，使用描述性的名称
2. 创建 `SKILL.md` 文件，包含 YAML 前置元数据：

```yaml
---
name: skill-name
description: 技能功能的简短描述
---

# 技能标题

## 使用时机
何时使用此技能...

## 处理流程
逐步说明...
```

3. 更新 `.claude-plugin/marketplace.json`，在 `plugins` 数组中注册新技能
4. 提交前彻底测试该技能

## 技能格式要求

- 必须包含 YAML 前置元数据，包含 `name` 和 `description`
- `name` 应使用 kebab-case 格式且保持唯一
- 技能内容必须使用中文编写
- 包含清晰的使用触发条件和处理流程步骤
- 适用时添加输出格式示例

## Marketplace 配置

`.claude-plugin/marketplace.json` 文件配置技能的加载方式。添加技能时：
- 在 `plugins` 数组中添加新条目
- 将 `source` 设置为 `"./"` 用于相对路径解析
- 在 `skills` 数组中添加技能路径（相对于 source）

## 无构建/测试命令

此仓库仅包含 Markdown 技能定义，不涉及构建、测试或 lint 命令。

## Git 提交规范

**在此仓库中创建 git 提交时，提交描述必须使用中文。**

- 提交消息应简洁明了，使用中文描述变更内容
- 例如：`添加 odoo-po-translator 技能`、`更新 README.md`、`添加 LICENSE 文件`
