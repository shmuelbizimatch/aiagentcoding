# AI-Coding-System

An intelligent system that transforms high-level project ideas into fully implemented applications using AI agents and the Cursor IDE. The system breaks down complex software requirements into manageable tasks, automatically generates code through AI assistance, and orchestrates the development process from concept to completion.

## Quickstart

Once the Product Agent is implemented, you can generate a PRD for your project idea:

```bash
# Install dependencies
pip install -r requirements.txt

# Set up your Claude API key
export ANTHROPIC_API_KEY="your-api-key-here"

# Generate a Product Requirements Document
python product_agent.py --idea "Build a task management web app" --output memory/

# Break down the PRD into actionable tasks
python task_agent.py --prd memory/task_management_prd.md --output memory/

# Execute the tasks using Cursor CLI
python runner.py --tasks memory/task_management_tasks.json
```

## Project Structure

```
.
├── memory/                       # will store PRDs, task JSON, and logs
├── prompts/                      # prompt templates for agents
├── src/                          # generated application code goes here
├── product_agent.py              # CLI script – generates PRD with Claude
├── task_agent.py                 # CLI script – breaks PRD into JSON tasks
├── runner.py                     # orchestrator – feeds tasks to Cursor CLI
├── run_cursor.sh                 # shell wrapper that runs a single task
├── requirements.txt              # deps: openai, python-dotenv, etc.
└── README.md                     # high-level overview
```

### Directory Descriptions

- **memory/**: Stores all generated artifacts including PRDs, task JSON files, and execution logs
- **prompts/**: Contains prompt templates used by the AI agents for consistent output generation
- **src/**: Target directory where the generated application code will be placed
- **product_agent.py**: CLI tool that takes project ideas and generates detailed PRDs using Claude
- **task_agent.py**: CLI tool that analyzes PRDs and breaks them down into structured, actionable tasks
- **runner.py**: Main orchestrator that executes tasks by interfacing with the Cursor CLI
- **run_cursor.sh**: Shell wrapper script that handles individual task execution and logging
- **requirements.txt**: Python dependencies required for the AI-Coding-System
