
# 🤖 Agentic RAG Chatbot for AI Talent Matching

This project implements an end-to-end **Agentic AI chatbot** that combines **LLMs, Retrieval-Augmented Generation (RAG)**, **semantic search**, and **real-time web tools** to match candidate profiles with job descriptions based on skills and city context. It is **memory-aware**, fully interactive, and built for intelligent human-like conversations.

---

## 🚀 Features

- ✅ Extracts structured data from candidate resumes (name, city, skills, phone, email)
- ✅ Generates embeddings for:
  - Full profile content
  - Skill + City combinations
- ✅ Stores all information in **MongoDB**, including raw profile text
- ✅ Converts user queries into embeddings and matches top candidates using vector similarity
- ✅ Embeds **job description PDFs** and performs RAG to match company needs
- ✅ Integrates **SERPAPI for real-time web search**
- ✅ AI agent with **tool-based reasoning** and **conversation memory**

---

## 📦 Tech Stack

- **LangChain** (agent, tools, memory, embeddings)
- **OpenAI GPT-4** (LLM and embeddings)
- **MongoDB** (structured and vector storage)
- **pdfplumber** (resume parsing)
- **scikit-learn** (cosine similarity)
- **SERPAPI** (web search integration)
- **Python** (CLI chatbot interface)

---

## 💡 Example Chat Flow

```
You: What are the top AI tools?
Bot: TensorFlow, PyTorch, Keras...

You: Which companies in my job folder need these skills?
Bot: DeepAI_Solutions – Bengaluru, VisionNext – Hyderabad...

You: Fetch top candidates from our database
Bot: Dr. Arjun Mehta, Dr. Neha Ramesh, Dr. T.K. Senthil Kumar...

You: Show me Senthil’s full profile
Bot: [Full profile text from MongoDB]

You: Get his LinkedIn
Bot: [Search result using SERPAPI]
```

---

## 🛠 How to Run

### 1. Set up the environment

```bash
pip install -r requirements.txt
```

Ensure the following packages are installed:
- langchain
- openai
- pymongo
- scikit-learn
- pdfplumber
- serpapi
- python-dotenv

### 2. Set your API keys

```bash
export OPENAI_API_KEY=your-key
export SERPAPI_API_KEY=your-key
```

You can also use a `.env` file.

### 3. Run pipeline in order

#### Step 1: Parse and Push Candidate Profiles to MongoDB

```bash
python push_to_mangodb.py
```

#### Step 2: Run Query and Matching Logic

```bash
python query_from_mongodb_with_llm.py
```

#### Step 3: Launch Agentic RAG Chatbot

```bash
python full_agent.py
```

---

## 🧠 Tools in the Agent

| Tool | Description |
|------|-------------|
| `Search Top Skills` | Uses SERPAPI to search web for trending AI skills |
| `Job Description Matcher` | Compares AI skills to job descriptions in PDF |
| `Candidate Matcher` | Fetches top matching candidates from MongoDB |
| `Resume Fetcher` | Retrieves full resume from MongoDB |

---

## 📁 Folder Structure

```
📂 JobDescriptions/          ← Sample job description PDFs
📂 short_profile/            ← Sample candidate profiles
📄 push_to_mangodb.ipynb     ← Resume parsing + embedding + MongoDB storage
📄 query_from_mongodb.ipynb  ← Embedding-based search and match logic
📄 full_agent.ipynb          ← Agentic AI chatbot with memory
📄 README.md                 ← You're here!
```

---

## 👤 Author

**Dr. T.K. Senthil Kumar**    
AI Educator | CV Expert | ML Practitioner  
📧 tkseneee@gmail.com  

---

## 🔐 Disclaimer

This project is for educational and research purposes. The AI agent respects privacy and ethical standards by design.

---

## 📌 Future Work

- Integrate voice/chat UI with Streamlit
- Add candidate ranking visualization
- Automate LinkedIn/GitHub verification

---

## ⭐ Star this repo if you find it useful. Contributions welcome!
