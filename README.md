# prompt-to-software

根据 Recipkg 软件配方及全部递归依赖重建软件，生成实现并实际验证验收条件。用于提示词到软件、从配方构建或验证重建完整性的需求。

Read [SKILL.md](SKILL.md) for the workflow and linked resources. This is the canonical standalone skill repository used by [Recipkg](https://github.com/recipkg/recipkg).

For stateful interfaces, verify real browser tasks against isolated data and check persisted state, including responsive and error states. Report skipped checks and distinguish observations of the original application from acceptance of a reconstruction.

For state updates, compare complete before-and-after data for the defined interfaces and permissions, including relevant omitted and empty fields; recheck persistence when required. Treat unspecified behavior as a recipe gap.

Before black-box acceptance, verify which candidate and helper executables actually run. A missing or silently substituted target is a failure; report skipped tests and deliberately used external tools.

## Use as a project submodule

```sh
git submodule add https://github.com/recipkg/prompt-to-software.git .agents/skills/prompt-to-software
git submodule update --init --recursive
```

Keep the same repository across projects. Review upstream changes and local work before checking out a new commit, then explicitly commit the consumer gitlink. Do not copy and hand-maintain a second skill or overwrite custom modifications.

This repository is also a Markdown-only Recipkg skill recipe: validate with `recipkg check .`, then pack it outside this directory. [License](LICENSE.md).

## 中文

本仓库只维护 `prompt-to-software` 技能。不同项目应把此同一仓库作为固定提交的 Git 子模块引用，不复制技能正文。修改先回本仓库，再更新项目指针；注意保护本地改动。技能入口与说明见 [SKILL.md](SKILL.md)。

有状态界面要在隔离数据上实际运行浏览器任务，并检查持久化状态、宽窄视口和错误状态。记录跳过的检查，区分上游观察与重建软件验收。

对状态更新，按配方中的接口和权限比较完整的更新前后数据，覆盖相关的省略和空字段，并在需要时重启复查；未定义行为作为配方缺口处理。

黑盒验收前确认实际运行的重建程序和辅助工具；目标缺失或被静默替换时应失败，并记录跳过的测试和有意使用的外部工具。
