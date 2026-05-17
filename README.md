**Runnable in LangChain**
## What is Runnable?
Runnable is a standardized executable component in LangChain that takes input, processes it, and returns output.

# Types of Runnable
Runnable in LangChain is mainly divided into 2 categories:
1. Runnable Primitives
2. Task-Specific Runnables

   
# Runnable Tree Diagram
Runnable
│
├── Runnable Primitives
│   │
│   ├── RunnableSequence
│   ├── RunnableParallel
│   ├── RunnableLambda
│   └── RunnablePassthrough
│
└── Task-Specific Runnables
    │
    ├── Prompt Templates
    ├── Chat Models / LLMs
    ├── Retrievers
    ├── Output Parsers
    └── Tools

   
# 1. Runnable Primitives
These are basic building blocks used to create workflows and pipelines.

## Subparts of Runnable Primitives
### 1. RunnableSequence
* Executes tasks step-by-step.
* Output of one component becomes input of next.

Example Flow: prompt | model | parser

### 2. RunnableParallel
* Runs multiple tasks simultaneously.
* Useful for faster execution.
  
### 3. RunnableLambda
* Converts a normal Python function into a runnable.
* Useful for custom logic.
  example
from langchain_core.runnables import RunnableLambda
def upper(text):
    return text.upper()
  
### 4. RunnablePassthrough
* Passes input unchanged.
* Useful when original input is needed later.
  
# 2. Task-Specific Runnables
These are prebuilt runnable components designed for AI-related tasks.

## Subparts of Task-Specific Runnables

### 1. Prompt Templates
* Used to create structured prompts.

### 2. Chat Models / LLMs
* Generate AI responses.
* Example: Gemini, OpenAI.

### 3. Retrievers
* Retrieve relevant documents from vector databases.
* Mainly used in RAG.

### 4. Output Parsers
* Convert model output into structured format.
* Example: JSON, text, lists.

### 5. Tools
 Allow AI to use external systems.
 Example:
   Calculator
   Search API
   Database


# Key Benefits of Runnable

* Standard execution system
* Easy pipeline creation
* Supports streaming
* Supports async execution
* Reusable and modular
* Important for RAG and AI agents

