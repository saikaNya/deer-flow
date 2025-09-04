# Deer Flow 工作流程图文档

## 概述
本目录包含了Deer Flow项目的LangGraph工作流程图的多种表示形式，帮助理解整个系统的执行流程。

## 文件说明

### 1. workflow_diagram.md
- **描述**: 基础工作流程图，由LangGraph自动生成
- **格式**: Mermaid格式
- **内容**: 包含所有节点和连接关系
- **用途**: 了解完整的图结构

### 2. workflow_diagram_with_memory.md
- **描述**: 带内存版本的工作流程图
- **格式**: Mermaid格式
- **内容**: 与基础版本相同，但支持状态持久化
- **用途**: 了解支持记忆的工作流

### 3. detailed_workflow_diagram.md
- **描述**: 详细工作流程图，包含条件分支说明
- **格式**: Mermaid格式 + 详细文档
- **内容**: 
  - 主流程图（带条件分支）
  - 状态流转图
  - 节点功能详细说明
  - 错误处理机制
- **用途**: 深入理解工作流逻辑

### 4. simple_workflow_diagram.md
- **描述**: 简化的核心流程图
- **格式**: Mermaid格式
- **内容**: 突出主要执行路径
- **用途**: 快速理解核心流程

## 如何查看流程图

### 在线查看
1. 复制Mermaid代码块内容
2. 访问 [Mermaid Live Editor](https://mermaid.live/)
3. 粘贴代码并查看渲染结果

### 本地查看
1. 安装Mermaid CLI:
   ```bash
   npm install -g @mermaid-js/mermaid-cli
   ```
2. 生成图片:
   ```bash
   mmdc -i workflow_diagram.md -o workflow_diagram.png
   ```

### 在Markdown中查看
支持Mermaid的Markdown编辑器（如Typora、Mark Text）可以直接渲染流程图。

## 节点说明

### 主要节点类型
- **协调器 (coordinator)**: 用户交互入口
- **背景调研 (background_investigator)**: 信息收集
- **规划器 (planner)**: 计划生成
- **人工反馈 (human_feedback)**: 用户确认
- **研究团队 (research_team)**: 任务协调
- **研究员 (researcher)**: 研究执行
- **编程员 (coder)**: 代码执行
- **报告员 (reporter)**: 报告生成

### 连接类型
- `-->`: 直接连接
- `-.->`: 条件连接（虚线）

## 状态管理

### 关键状态字段
- `locale`: 用户语言环境
- `research_topic`: 研究主题
- `observations`: 观察结果
- `current_plan`: 当前计划
- `final_report`: 最终报告

## 重新生成流程图

如果需要重新生成流程图，运行：

```bash
# 激活虚拟环境
source .venv/bin/activate

# 运行导出脚本
python export_graph.py
```

## 注意事项

1. **依赖要求**: 需要安装LangGraph和相关依赖
2. **PNG导出**: 需要额外安装pygraphviz
3. **版本兼容**: 流程图基于当前代码版本生成
4. **更新频率**: 代码变更后建议重新生成流程图

---
*文档生成时间: $(date)*
*作者: heyi*
