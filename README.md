# Mazda Car Manual Assistant

A Retrieval-Augmented Generation (RAG) system that answers questions about a Mazda car manual.  

## Project Overview

This project demonstrates a simple two-agent RAG workflow:  

1. **Retrieval Agent**  
   
   - Searches the car manual using embeddings  
   - Returns the most relevant text chunks  

2. **Answer Agent**  
   
   - Uses an LLM to summarize the retrieved chunks  
   - Produces a clear answer based only on the manual  

An orchestrator coordinates both agents.  



## Architecture

User Question  
│  
▼  
Retrieval Agent  
(Embedding search)  
│  
▼  
Relevant Manual Chunks  
│  
▼  
Answer Agent (LLM)  
│  
▼  
Final Answer



## Tech Stack

- Python  
- SentenceTransformers  
- FAISS  
- Groq LLM API  
- Jupyter Notebook  
  
  

## Setup (Groq API key + Colab Secrets)

This notebook requires a **Groq API key** to call the LLM.  

### 1. Obtain a Groq API Key

Create an account and generate an API key at:  
https://console.groq.com/  

### 2. Add the API Key to Colab Secrets

In Google Colab:  

1. Click the **🔑 Secrets** icon in the left sidebar.  
2. Add a new secret with the name:  

GROQ_API_KEY

3. Paste your Groq API key as the value.  
4. Enable **"Notebook access"** for the secret.  

The notebook retrieves the key securely using:  

```python  
from google.colab import userdata
api_key = userdata.get("GROQ_API_KEY")
```

## Usage (run notebook in Colab)

This project is implemented as a **Jupyter Notebook designed to run in Google Colab**.  

### Steps

1. Open the notebook in **Google Colab**.  
2. Upload the required car manual PDF when prompted (if applicable).  
3. Run the cells sequentially from top to bottom to:  
   - Process the manual  
   - Generate embeddings  
   - Build the retrieval system  
4. Use the assistant function at the end of the notebook to ask questions about the manual.  

Example:  

```python  
car_manual_assistant("How do I reset the tire pressure warning?")
```

The system will retrieve relevant sections of the manual and generate an answer based on them.



## Files

- `2021-mazda2_manual_assistant.ipynb` – full implementation


