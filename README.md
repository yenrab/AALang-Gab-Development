# GAB - Generic AALang Builder

**GAB** (Generic AALang Builder) is an intelligent agent compiler that helps you build AALang-based products including tools, games, agents, protocols, and more. GAB uses a structured 4-mode workflow to guide you through the entire development process, from initial concept to final product.

## What is AALang?

**AALang** (Actor-based Agent Language) is a programming language designed specifically for LLM agent consumption and execution. It's optimized for graph-native, LLM-friendly development and supports bounded non-determinism. AALang is **MCP (Model Context Protocol) and A2A (Agent to Agent) ready**, making it perfect for integration with modern LLM tooling and distributed agent systems.

**Is AALang Turing complete?** See the [arguments and analysis](turing-complete.md).

**Is AALang truly concurrent, or just pretending?** Explore the [concurrency and parallelism analysis](concurrent-parallel.md).

Learn more at: **[https://aalang.org](https://aalang.org)**

## What Can You Build with GAB?

**AALang is a general-purpose programming language** - you can build virtually anything that can be expressed computationally. GAB helps you create:

- **🎮 Games** - Interactive games powered by LLM agents
- **🛠️ Tools** - Utilities and applications that leverage LLM capabilities
- **🤖 Agents** - Custom LLM agents with specific behaviors and modes
- **📋 Protocols** - Communication and interaction protocols
- **💬 Communication Patterns** - Patterns for agent-to-agent or agent-to-user communication
- **📦 Any AALang-based Product** - Anything that conforms to AALang specifications

## Learn More

- **AALang Website**: [https://aalang.org](https://aalang.org)
- **Turing Completeness Analysis**: [Is AALang probabilistically Turing complete?](turing-complete.md) - Deep dive into AALang's computational capabilities
- **Concurrency and Parallelism Analysis**: [Is AALang truly concurrent, or just pretending?](concurrent-parallel.md) - Examination of AALang's concurrent/parallel architecture
- **Documentation**: See the specification files for detailed technical information

## How GAB Works

GAB uses a **4-mode-13-actor** pattern with a structured workflow:

### 1. **Clarification Mode** 🔍
- Analyzes your initial product description
- Identifies ambiguities and missing information
- Asks targeted questions to understand requirements
- Calculates understanding confidence scores
- Ensures you have a clear vision before proceeding

### 2. **Discussion Mode** 💬
- Decomposes the problem into manageable components
- Designs the architecture (modes, actors, personas)
- Proposes solutions and alternatives
- Facilitates consensus between personas
- Creates the initial design specification

### 3. **Formalization Mode** ✅
- Analyzes the design for logic errors and inconsistencies
- Verifies AALang design compliance
- Checks for common bugs and edge cases
- Ensures quality and completeness
- Finalizes the specification

### 4. **Generation Mode** 🚀
- Creates the final AALang product files
- Generates JSON-LD formatted specifications
- Implements all designed components
- Produces ready-to-use AALang code

## Getting Started

### Prerequisites

- An LLM that can execute JSON-LD based prompts (e.g., Claude, GPT-4)
- Access to the GAB specification files

### Using GAB

1. **Load GAB**: Add the `*.jsonld` files into your LLM environment. The `*gab.jsonld*` file is the instruction file, the others are data files it needs. If you are in a tool like cursor, drag `*gab.jsonld*` into an empty chat and hit enter. If you are a standard LLM tool like gemini or ChatGPT, add all the files to a chat and indicate that `*gab.jsonld*` is the execution instructions. Gab works best in cursor-like tools.
2. **Describe Your Idea**: Tell GAB what you want to build
3. **Follow the Workflow**: GAB will guide you through Clarification → Discussion → Formalization → Generation
4. **Get Your Product**: Receive a complete AALang specification ready to use! Note: Your product is complete. None of the `* *.json*` or other files in this distribution are distributed with your product. 

### Example Interaction

```
You: "I want to create a number guessing game where the LLM thinks of a number 
      and the user tries to guess it."

GAB: [Clarification Mode]
     "I understand you want a number guessing game. To clarify:
     - Should the number range be configurable?
     - How many guesses should the user have?
     - Should there be hints?"
     
You: [Answer questions]

GAB: [Discussion Mode]
     "Based on your answers, I propose a 2-mode architecture:
     - Setup Mode: Configure game parameters
     - Game Mode: Play the guessing game
     ..."
     
GAB: [Formalization Mode]
     "Analyzing the design for issues..."
     
GAB: [Generation Mode]
     "Generating your number-guessing-game.jsonld file..."
```

## Building Specific Product Types

### Creating Games

GAB excels at creating interactive games. Simply describe your game concept, and GAB will:
- Design the game modes and states
- Create actor personas for game logic
- Implement user interaction patterns
- Generate the complete game specification

**Example**: "Create a trivia game with multiple categories and difficulty levels"

### Creating Tools

Build tools that leverage LLM capabilities:
- Describe the tool's purpose
- Specify input/output requirements
- Define the workflow
- GAB generates the tool specification

**Example**: "Create a code review tool that analyzes code and provides suggestions"

### Creating Agents

Design custom LLM agents for specific tasks:
- Define the agent's purpose
- Specify modes and behaviors
- Design persona interactions
- Generate the agent specification

**Example**: "Create a customer support agent that handles common questions"

### Executing AALang Code

Once GAB generates your AALang specification:

1. **Load the Generated File**: Load the `.jsonld` file into your LLM
2. **Execute**: The LLM interprets and executes the AALang code
3. **Interact**: Use the product as designed

AALang specifications are **MCP and A2A ready**, meaning they integrate seamlessly with Model Context Protocol tooling for enhanced LLM interactions and support native Agent-to-Agent communication via gossip-based P2P protocols for distributed execution.

## User Commands

GAB supports several commands for managing your building process:

### Decision Management
- `undo` - Undo the most recent decision
- `rollback to [N]` - Roll back to decision number N
- `show decisions` - View complete decision history

### Actor Management
- `load actors` - Load all actors from generated .jsonld files
- `unload actors` - Return to builder-only mode
- `self-check actors` - Have loaded actors analyze their own instructions
- `skip formalization` - Explicitly authorize skipping Formalization Mode (Generation Mode is still mandatory)

## File Structure

```
AALang-Gab-Development/
├── gab.jsonld              # Main GAB agent specification
├── gab-runtime.jsonld      # Runtime behaviors and instructions
├── gab-formats.jsonld      # Output and logging format definitions
├── aalang-design.jsonld    # Core AALang design specifications
├── agent-to-actor.jsonld   # Agent-to-actor communication protocols
├── message-protocol.jsonld # Message and state management protocols
├── turing-complete.md      # Analysis of AALang's probabilistic Turing completeness
├── concurrent-parallel.md # Analysis of AALang's concurrency and parallelism
├── LICENSE                 # License information
└── README.md               # This file
```

## Key Features

- **Structured Workflow**: Clear progression through Clarification → Discussion → Formalization → Generation
- **Quality Assurance**: Built-in checks for logic errors, edge cases, and AALang compliance
- **Decision Tracking**: All decisions are logged for review and rollback
- **Persona-Based Design**: Multiple personas provide diverse perspectives
- **MCP & A2A Ready**: Generated products work seamlessly with Model Context Protocol and support Agent-to-Agent communication for distributed execution
- **Flexible**: Build games, tools, agents, protocols, and more

## License

Copyright (c) 2025 Lee S. Barney

This software may be used, modified, and distributed for private, educational, and business purposes. The software files, modified versions, portions, and derivatives may NOT be sold or commercialized. Products built with AALang/GAB may be sold without restriction.

See [LICENSE](LICENSE) for full details.

---

**Ready to build?** Load `gab.jsonld` and start describing your idea!

