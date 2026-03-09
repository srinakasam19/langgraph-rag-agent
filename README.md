# LangGraph RAG Agent with Gemini & FAISS

## Overview

This project demonstrates a **Retrieval-Augmented Generation (RAG)
agent** built using:

-   LangGraph (agent workflow)
-   LangChain (LLM integration)
-   Google Gemini (LLM + embeddings)
-   FAISS (vector database)

The agent can **decide whether it needs to retrieve documents** before
answering a question.

This project shows how modern **AI agents combine retrieval and
generation** to produce accurate answers.

------------------------------------------------------------------------

## Architecture

User Question\
↓\
Decision Node (decide if retrieval is needed)\
↓\
Retriever (FAISS vector search)\
↓\
Relevant Documents\
↓\
Gemini LLM generates final answer

------------------------------------------------------------------------

## Technologies Used

-   Python
-   LangChain
-   LangGraph
-   FAISS Vector Database
-   Google Gemini API
-   Google Generative AI Embeddings

------------------------------------------------------------------------

## Project Structure

    rag-langgraph-agent/
    │
    ├── notebook.ipynb
    ├── requirements.txt
    ├── README.md
    └── data/

------------------------------------------------------------------------

## Installation

Install dependencies:

``` bash
pip install langchain
pip install langgraph
pip install langchain-google-genai
pip install faiss-cpu
pip install google-genai
```

------------------------------------------------------------------------

## Setup API Key

Set your Google API key:

``` python
import os
os.environ["GOOGLE_API_KEY"] = "YOUR_API_KEY"
```

You can generate a key from:

https://aistudio.google.com/app/apikey

------------------------------------------------------------------------

## How It Works

### 1. Documents are converted into embeddings

Gemini embedding model converts text into vector representations.

### 2. Vectors are stored in FAISS

FAISS enables fast similarity search between the question and stored
documents.

### 3. The agent decides whether retrieval is needed

A decision node checks if the question requires document retrieval.

### 4. Documents are retrieved

If required, the retriever fetches the most relevant documents.

### 5. Gemini generates the answer

The LLM generates the final response using the retrieved context.

------------------------------------------------------------------------

## Example

Question:

    What is LangGraph?

Retrieved context:

    LangGraph is a framework built on top of LangChain that helps developers design workflows as graphs.

Answer:

    LangGraph is a framework built on top of LangChain that allows developers to create stateful AI workflows using graph-based execution.

------------------------------------------------------------------------

## Workflow Graph

               ┌───────────┐
               │  decide   │
               └─────┬─────┘
                     │
            needs retrieval?
              │           │
              ▼           ▼
         retrieve      generate
              │           │
              └──────► generate
                         │
                        END

------------------------------------------------------------------------

## Features

-   Agent-based RAG pipeline
-   Document retrieval with FAISS
-   Gemini-powered LLM responses
-   Conditional retrieval workflow
-   LangGraph-based orchestration

------------------------------------------------------------------------

## Future Improvements

-   Add document loaders (PDF / Web)
-   Add memory for conversations
-   Implement advanced RAG techniques
-   Add evaluation metrics

------------------------------------------------------------------------

## Author

Developed as part of learning **AI agents, LangGraph workflows, and RAG
systems**.
