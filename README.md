# LLM-Powered Chatbot

A hands-on project exploring LangChain's core capabilities through two interactive Jupyter notebooks: a **conversational chatbot** with session memory and a **retrieval-augmented generation (RAG)** pipeline using vector stores.

## Project Structure

```
LLM-powered-chatbot/
├── chatbots.ipynb          # Conversational chatbot with message history
├── vectorretriever.ipynb   # Vector store, retrievers, and RAG pipeline
├── requirements.txt        # Python dependencies
├── .env                    # API keys (not tracked by git)
└── .gitignore
```

## Notebooks

### 1. Chatbots (`chatbots.ipynb`)

Builds a conversational chatbot powered by Groq's Llama 3.1 model. Covers:

- **Basic chat** — Sending and receiving messages with `ChatGroq`.
- **Message history** — Using `RunnableWithMessageHistory` and `ChatMessageHistory` to maintain separate conversation sessions via session IDs.
- **Prompt templates** — Structuring system instructions and user messages with `ChatPromptTemplate` and `MessagesPlaceholder`.
- **Multi-language support** — Parameterizing the prompt to respond in a specified language.
- **Conversation trimming** — Managing context window limits with `trim_messages` to keep only the most recent messages.

### 2. Vector Store & Retrievers (`vectorretriever.ipynb`)

Demonstrates LangChain's retrieval abstractions for RAG workflows. Covers:

- **Documents** — Creating `Document` objects with content and metadata.
- **Embeddings** — Generating vector embeddings using HuggingFace's `all-MiniLM-L6-v2` model.
- **Vector store** — Storing and querying documents with Chroma (similarity search, scored search, async search).
- **Retrievers** — Wrapping vector stores as LangChain `Runnable` objects for use in LCEL chains.
- **RAG chain** — Combining a retriever, prompt template, and LLM into a full retrieval-augmented generation pipeline.

## Prerequisites

- Python 3.12+
- A [Groq API key](https://console.groq.com/)
- A [HuggingFace token](https://huggingface.co/settings/tokens) (for the embeddings model)

## Setup

1. **Clone the repository**

   ```bash
   git clone https://github.com/sothulthorn/LLM-powered-chatbot.git
   cd LLM-powered-chatbot
   ```

2. **Create and activate a virtual environment**

   ```bash
   python -m venv .venv
   # Windows
   .venv\Scripts\activate
   # macOS / Linux
   source .venv/bin/activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Configure environment variables**

   Create a `.env` file in the project root:

   ```
   GROQ_API_KEY=your_groq_api_key
   HF_TOKEN=your_huggingface_token
   ```

5. **Run the notebooks**

   ```bash
   jupyter notebook
   ```

   Open either `chatbots.ipynb` or `vectorretriever.ipynb` to get started.

## Key Technologies

| Technology | Purpose |
|---|---|
| [LangChain](https://python.langchain.com/) | LLM application framework |
| [Groq](https://groq.com/) | LLM inference (Llama 3.1) |
| [Chroma](https://www.trychroma.com/) | Vector database |
| [HuggingFace](https://huggingface.co/) | Text embeddings (`all-MiniLM-L6-v2`) |
| [python-dotenv](https://pypi.org/project/python-dotenv/) | Environment variable management |

## License

This project is for educational purposes.
