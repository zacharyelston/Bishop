# Bishop: The Orchestrator of Digital Zealots

## Historical Context and Metaphor

In religious history, zealots were fervent believers who executed tasks with unwavering dedication and passionate intensity. They required direction, purpose, and divine instruction from church leadership - the bishops - who provided strategic guidance, interpreted sacred texts, and channeled their zealous energy toward meaningful objectives.

Just as biblical zealots were "zealous on behalf of God" and required religious leadership to channel their fervor productively, bishops served as the intermediaries who transformed raw devotion into organized action. The Zealots' passionate intensity needed careful direction - without proper guidance, their zeal could become destructive rather than constructive.

## Bishop: The Technical Implementation

**Bishop** is a specialized fork of [DevOpsZealot](https://github.com/zacharyelston/DevOpsZealot) that serves as the high-level orchestrator. While DevOpsZealot executes code changes autonomously, Bishop focuses on understanding requirements, planning work, and overseeing execution.

## Architecture

Bishop shares the same core architecture as DevOpsZealot but with a completely different mission:

```
┌─────────────────────────────────────────────────────────────┐
│                         BISHOP WORKFLOW                       │
├─────────────────────────────────────────────────────────────┤
│                                                               │
│  1. READ PHASE (Sacred Texts)                                │
│     Redmine API → Issue Fetching → Context Gathering         │
│                                                               │
│  2. RESEARCH PHASE (Divine Study)                            │
│     Issue Analysis → Related Issues → Documentation Search   │
│     Code Repository Analysis → Pattern Recognition           │
│                                                               │
│  3. DELIBERATION PHASE (Council of Models)                   │
│     Multiple LLMs → Different Contexts → Task Generation     │
│     ├── GPT-4: Business Requirements Analysis                │
│     ├── Claude: Technical Implementation Details             │
│     └── Local LLM: Security & Compliance Check               │
│                                                               │
│  4. REVIEW PHASE (Human Blessing)                            │
│     Task Proposals → Human Review Interface → Approval       │
│                                                               │
│  5. ASSIGNMENT PHASE (Divine Instruction)                    │
│     Final Task Creation → DevOpsZealot Assignment            │
│     Detailed Instructions → Success Criteria                 │
│                                                               │
│  6. OVERSIGHT PHASE (Pastoral Care)                          │
│     Monitor Zealot Execution → Review Results                │
│     Performance Rating → Feedback Loop                       │
│     Update Redmine → Close Loop                              │
│                                                               │
└─────────────────────────────────────────────────────────────┘
```

## Core Differences from DevOpsZealot

While Bishop shares DevOpsZealot's codebase, it operates with fundamentally different:

### **Rules**
- Bishop cannot directly modify code - it only creates instructions
- Bishop must get human approval before assigning tasks
- Bishop evaluates work rather than executing it

### **Context**
- Bishop works with Redmine issues, not git repositories
- Bishop focuses on requirements and planning, not implementation
- Bishop considers multiple perspectives through different LLMs

### **Outputs**
- Bishop produces task definitions, not code changes
- Bishop generates performance reviews, not pull requests
- Bishop updates issue tracking, not git commits

## Key Components (Adapted from DevOpsZealot)

### Core System (src/bishop/)
- **Redmine Client**: Interface with Redmine API for issue management
- **Research Engine**: Gathers context from multiple sources
- **LLM Orchestrator**: Manages multiple AI models for different perspectives
- **Review Interface**: Human approval workflow for task assignments
- **Task Generator**: Creates detailed instructions for DevOpsZealot
- **Performance Evaluator**: Reviews and rates zealot work

### Shared Components (from DevOpsZealot)
- **AI Integration**: Multi-model support with different prompts
- **Container Management**: Isolated environments for analysis
- **Monitoring**: Metrics and observability
- **Config Management**: Environment and API configurations

## Workflow Example

```python
# Bishop reads a Redmine issue
issue = bishop.read_redmine_issue(issue_id=1234)

# Research and gather context
context = bishop.research_phase(
    issue=issue,
    search_related=True,
    analyze_codebase=True
)

# Generate task proposals using multiple LLMs
proposals = bishop.deliberation_phase(
    issue=issue,
    context=context,
    models=['gpt-4', 'claude', 'local-llm']
)

# Present for human review
approved_task = bishop.human_review(proposals)

# Assign to DevOpsZealot
zealot_job = bishop.assign_to_zealot(
    task=approved_task,
    zealot_id='zealot-001'
)

# Monitor and evaluate
result = bishop.monitor_execution(zealot_job)
performance = bishop.evaluate_performance(result)
bishop.update_redmine(issue_id=1234, status='completed', rating=performance)
```

## What Bishop Orchestrates

Bishop can orchestrate DevOpsZealot to work on any type of code:
- **Application Code**: Features, bug fixes, refactoring
- **Infrastructure as Code**: Terraform, CloudFormation, Ansible
- **Configuration Files**: YAML, JSON, TOML configurations
- **Scripts**: Bash, Python, PowerShell automation
- **Documentation**: Markdown, API docs, technical guides
- **Test Code**: Unit tests, integration tests, E2E tests
- **CI/CD Pipelines**: GitHub Actions, Jenkins, GitLab CI

If it's code in a git repository, DevOpsZealot can work on it, and Bishop can orchestrate it.

## Installation

*Note: Bishop is a fork of DevOpsZealot. Most setup is identical.*

```bash
# Clone repository
git clone https://github.com/zacharyelston/Bishop.git
cd Bishop

# Create virtual environment
python -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
pip install -e .

# Set up environment
cp .env.example .env
# Edit .env with your API keys (Redmine, OpenAI, Claude, etc.)

# Run tests
pytest

# Start Bishop server
python -m bishop.server
```

## Configuration

Bishop requires additional configuration beyond DevOpsZealot:

```env
# Redmine Configuration
REDMINE_URL=https://your-redmine-instance.com
REDMINE_API_KEY=your-api-key

# Multiple LLM Configurations
OPENAI_API_KEY=your-openai-key
ANTHROPIC_API_KEY=your-claude-key
LOCAL_LLM_ENDPOINT=http://localhost:11434

# Bishop-specific settings
BISHOP_REVIEW_REQUIRED=true
BISHOP_MIN_LLM_CONSENSUS=2
BISHOP_PERFORMANCE_THRESHOLD=0.8
```

## The Religious Hierarchy in Code

- **Zealots** ([DevOpsZealot](https://github.com/zacharyelston/DevOpsZealot)) - The passionate executors of code changes
- **Bishop** - The wise orchestrator providing direction and purpose
- Future possibilities: 
  - **Cardinal** - Multi-organization orchestration layer
  - **Pope** - Enterprise governance and policy layer

## Development Roadmap

### Phase 1: Foundation (Fork & Adapt)
- [ ] Fork DevOpsZealot codebase
- [ ] Replace git operations with Redmine API client
- [ ] Adapt task structure for instruction generation
- [ ] Remove direct code modification capabilities

### Phase 2: Intelligence (Multi-Model Deliberation)
- [ ] Implement multi-LLM orchestration
- [ ] Create context-specific prompts for each model
- [ ] Build consensus mechanism for task generation
- [ ] Add research engine for gathering context

### Phase 3: Human Interface
- [ ] Build review interface for task approval
- [ ] Create dashboard for monitoring zealot performance
- [ ] Implement feedback collection system
- [ ] Add performance analytics

### Phase 4: Wisdom (Learning & Optimization)
- [ ] Pattern recognition across issues
- [ ] Performance-based model selection
- [ ] Automated context enrichment
- [ ] Predictive task complexity estimation

## Contributing

This project is in early development. Since Bishop is a fork of DevOpsZealot, contributions should consider compatibility with the parent project where appropriate.

## License

MIT License - See LICENSE file for details

## Related Projects

- [DevOpsZealot](https://github.com/zacharyelston/DevOpsZealot) - The autonomous AI-powered code editing tool that Bishop orchestrates

---

*"For zeal without knowledge is not good" - Proverbs 19:2*

*Bishop provides the knowledge to guide the zeal.*

Yes, we also named it after Lance Henriksen's Bishop character in the science fiction film Aliens (1986).
