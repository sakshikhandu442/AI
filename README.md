# 🤖 Autonomous AI Data Analyst

### Software and Tools Required
1. [GitHub Account](https://github.com)
2. [VS Code](https://code.visualstudio.com)
3. [Python 3.10+](https://www.python.org)
4. [OpenAI / Anthropic API Key](https://platform.openai.com) *(or preferred LLM provider)*

---

## 📌 Overview

**Autonomous AI Data Analyst** is an intelligent, agent-based system that automates end-to-end data analysis workflows. It accepts raw datasets, generates insights, performs statistical analysis, creates visualizations, and delivers a comprehensive narrative report — all autonomously, with minimal human intervention.

The system leverages Large Language Models (LLMs) as a reasoning engine, combined with a modular Python pipeline for data processing, tool-calling, and report generation.

---

## 🚀 Project Objectives

* Enable fully autonomous analysis of structured datasets
* Use LLM-powered agents to plan and execute analytical tasks
* Generate statistical summaries, correlations, and trend detection
* Produce publication-ready visualizations and written reports
* Build a scalable, extensible agent architecture

---

## 🧠 Problem Statement

Given any structured dataset (CSV / Excel / SQL), automatically:
- Understand the data schema and context
- Identify key patterns, anomalies, and insights
- Generate charts and statistical reports
- Summarize findings in plain English

---

## 🗂️ Project Structure

```
Autonomous-AI-Data-Analyst/
│
├── artifacts/                    # Generated outputs
│   ├── reports/
│   │   └── analysis_report.pdf
│   ├── charts/
│   │   ├── correlation_heatmap.png
│   │   └── trend_analysis.png
│   └── summaries/
│       └── insights.json
│
├── data/                         # Input datasets
│   ├── raw/
│   │   └── dataset.csv
│   └── processed/
│       └── cleaned_dataset.csv
│
├── src/
│   ├── agents/
│   │   ├── planner_agent.py      # High-level task planning
│   │   ├── analyst_agent.py      # Statistical analysis
│   │   ├── viz_agent.py          # Chart generation
│   │   └── report_agent.py       # Narrative report writing
│   │
│   ├── tools/
│   │   ├── data_loader.py        # CSV / Excel / SQL ingestion
│   │   ├── eda_tools.py          # Exploratory data analysis
│   │   ├── stats_tools.py        # Statistical computations
│   │   └── plot_tools.py         # Matplotlib / Seaborn wrappers
│   │
│   ├── pipeline/
│   │   └── analyst_pipeline.py   # Orchestration logic
│   │
│   ├── llm/
│   │   ├── llm_client.py         # LLM API wrapper
│   │   └── prompt_templates.py   # Agent prompts
│   │
│   ├── exception.py
│   ├── logger.py
│   └── utils.py
│
├── notebooks/                    # Experiments & prototypes
│   ├── 1. EDA_Exploration.ipynb
│   └── 2. Agent_Testing.ipynb
│
├── config/
│   └── config.yaml               # Model, paths, and settings
│
├── venv/
├── requirements.txt
├── setup.py
└── README.md
```

---

## ⚙️ Tech Stack

| Category | Tools |
|---|---|
| Language | Python 3.10+ |
| LLM Integration | OpenAI GPT-4o / Anthropic Claude |
| Data Processing | Pandas, NumPy |
| Visualization | Matplotlib, Seaborn, Plotly |
| Statistical Analysis | SciPy, Statsmodels |
| Agent Framework | LangChain / Custom Agent Loop |
| Report Generation | ReportLab / Jinja2 |
| Serialization | Pickle, JSON |

---

## 🔄 Agent Workflow

```
User Input (Dataset + Query)
        │
        ▼
  🧩 Planner Agent         → Breaks down the task into subtasks
        │
        ▼
  📊 Analyst Agent         → Runs EDA, statistics, correlation
        │
        ▼
  📈 Visualization Agent   → Generates charts and plots
        │
        ▼
  📝 Report Agent          → Writes narrative insights & summary
        │
        ▼
  📁 Output (PDF Report + Charts + JSON Insights)
```

---

## 📊 Capabilities

### Automated EDA
* Missing value detection and handling strategy
* Data type inference and schema profiling
* Outlier detection (IQR / Z-score methods)

### Statistical Analysis
* Descriptive statistics (mean, median, std, skewness)
* Correlation matrix and feature relationships
* Hypothesis testing (t-test, chi-square)
* Trend and seasonality detection

### Visualizations
* Distribution plots and histograms
* Correlation heatmaps
* Time-series trend lines
* Categorical comparison charts

### Report Generation
* Plain-English narrative of findings
* Highlighted anomalies and recommendations
* Exportable PDF with embedded charts

---

## 🧪 How to Run the Project

### Step 1: Clone the repository

```bash
git clone <your-repo-link>
cd Autonomous-AI-Data-Analyst
```

### Step 2: Create & activate virtual environment

```bash
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # macOS / Linux
```

### Step 3: Install dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Set your API key

```bash
# Windows
set OPENAI_API_KEY=your_api_key_here

# macOS / Linux
export OPENAI_API_KEY=your_api_key_here
```

### Step 5: Run the pipeline

```bash
python -m src.pipeline.analyst_pipeline --input data/raw/dataset.csv --query "Analyze sales trends and key drivers"
```

---

## 📈 Sample Output

After running the pipeline:

```
artifacts/
├── reports/
│   └── analysis_report.pdf      ← Full AI-generated report
├── charts/
│   ├── correlation_heatmap.png
│   ├── distribution_plots.png
│   └── trend_analysis.png
└── summaries/
    └── insights.json            ← Structured insights (machine-readable)
```

---

## 🔧 Configuration

Edit `config/config.yaml` to customize behavior:

```yaml
llm:
  provider: openai         # openai | anthropic
  model: gpt-4o
  temperature: 0.2
  max_tokens: 4096

analysis:
  outlier_method: iqr      # iqr | zscore
  correlation_threshold: 0.7

output:
  format: pdf              # pdf | html | markdown
  chart_dpi: 150
```

---

## 📌 Key Highlights

* Fully autonomous multi-agent architecture
* LLM-powered reasoning for adaptive analysis
* Tool-calling enables real Python execution
* Handles diverse dataset types and domains
* Human-readable reports with actionable insights
* Modular design — easy to extend with new tools

---

## ⚠️ Common Issues & Fixes

| Issue | Solution |
|---|---|
| API key not found | Set `OPENAI_API_KEY` as environment variable |
| File not found error | Ensure dataset path is correct in config |
| Rate limit exceeded | Add retry logic or reduce request frequency |
| Empty charts generated | Check for sufficient non-null data in columns |
| Import errors | Run using `python -m` from project root |
| LLM hallucinating schema | Provide explicit column descriptions in query |

---

## 📚 Future Improvements

* Natural language querying via chat interface (Streamlit / Gradio UI)
* Multi-dataset joining and cross-analysis
* Automated feature engineering recommendations
* SQL database connectivity (PostgreSQL, BigQuery)
* Scheduled report generation with email delivery
* Support for real-time streaming data
* Docker containerization & cloud deployment

---

## 🏗️ Architecture Overview

```
┌──────────────────────────────────────────────────┐
│                  User Interface                   │
│          (CLI / API / Web Dashboard)              │
└─────────────────────┬────────────────────────────┘
                      │
┌─────────────────────▼────────────────────────────┐
│               Orchestration Layer                 │
│              (analyst_pipeline.py)                │
└──────┬──────────┬──────────┬──────────┬──────────┘
       │          │          │          │
  ┌────▼───┐ ┌───▼────┐ ┌───▼────┐ ┌───▼────┐
  │Planner │ │Analyst │ │  Viz   │ │Report  │
  │ Agent  │ │ Agent  │ │ Agent  │ │ Agent  │
  └────────┘ └────────┘ └────────┘ └────────┘
       │          │          │          │
┌──────▼──────────▼──────────▼──────────▼──────────┐
│                   Tool Layer                      │
│     (data_loader, eda_tools, stats, plot)         │
└───────────────────────────────────────────────────┘
```

---

## 👨‍💻 Author

**Sakshi Khandu**

---

## ⭐ Acknowledgements

* OpenAI & Anthropic for LLM APIs
* LangChain for agent tooling patterns
* Scikit-learn & SciPy communities
* Kaggle for open datasets

---

## 📬 Contact

Feel free to connect for collaboration, queries, or contributions.

---

## 📄 License

This project is licensed under the MIT License. See `LICENSE` for details.