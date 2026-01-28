# Artificial Intelligence — Day 1

## What is Human Intelligence?

Human intelligence refers to the natural mental ability of humans to think, understand, learn, reason, and solve problems effectively.  
It includes creativity, decision-making skills, emotional awareness, and the ability to adapt to new and changing situations.

Human intelligence is shaped by several factors, including:

- Biological functioning of the brain  
- Life experiences  
- Surrounding environment  
- Cultural background  

Unlike machines, human intelligence is flexible, conscious, and multi-dimensional.  
It enables effective communication, social interaction, and innovation, allowing humans to function and evolve in the real world.

---

# Neural Networks and Deep Learning

## What is a Neural Network?

A Neural Network (NN) is a computer model inspired by the human brain.  
Just like the human brain has neurons that pass signals, a neural network contains artificial neurons that process data and learn patterns.

---

## How a Neural Network Works

- **Input Layer** → Receives data  
- **Hidden Layer(s)** → Learns patterns  
- **Output Layer** → Produces the result  

Example inputs include numbers, images, text, and voice.

---

## Example of a Neural Network

### Email Spam Detection

- **Input:** Email text  
- The neural network learns patterns such as keywords and sender behavior  
- **Output:** Spam or Not Spam  

---

## Use Cases of Neural Networks

- Used in spam filtering  
- Used in predicting house prices  
- Helps detect fraud in banking systems  
- Used for simple image recognition such as recognizing handwritten digits  

---

## What is Deep Learning?

Deep Learning is a subset of neural networks that uses many hidden layers, also called deep neural networks.

**Note:**  
All deep learning models are neural networks, but not all neural networks are deep learning models.

---

## Why Is It Called "Deep"?

- Uses multiple hidden layers (10, 50, 100+)  
- Can learn very complex patterns  
- Works well with large amounts of data  

---

## Example of Deep Learning

### Face Recognition

- **Input:** Photo  
- The deep neural network learns:
  - Edges  
  - Eyes  
  - Nose  
  - Full face  
- **Output:** Person identified  

This task requires many layers, which is why it is considered deep learning.

---

## Use Cases of Deep Learning

- Facial recognition systems  
- Voice assistants like Alexa and Google Assistant  
- Language translation and chatbots  
- Self-driving cars  
- Medical image analysis  

---

## Summary

- A neural network is a brain-inspired model that learns patterns from data and works well for simpler problems.  

- Deep learning is an advanced form of neural networks that uses many layers to solve complex problems.  

- Neural networks are suitable when data and complexity are limited.  

- Deep learning is preferred when data is large and high accuracy is required.


# 📅 DAY 2 — Tokens, Transformers, and Parallelism

## What Is a Token?

In large language models, a token is the smallest piece of text that the model can recognize and process.  
Instead of reading full sentences like humans, models first split text into tokens.

A token may represent:
- A complete word  
- A fragment of a word  
- Punctuation marks  
- Spaces or special characters  

### Example

Sentence:  
“Apple is green.”

After tokenization, it may become:  
Apple, is, green, . → **4 tokens**

Each token is mapped to a numerical value such as:  
[5271, 181, 4490, 13]

Since language models operate on numbers, all text is converted into numeric form before processing.  
While generating responses, the model predicts one token at a time using previously generated tokens.

Tokenization directly impacts:
- Processing cost  
- Response speed  
- Context length  
- Multilingual support  

Modern LLMs have defined token limits (for example, 128K tokens), which decide how much information the model can keep in memory during a conversation.

---

## What Is a Transformer?

A transformer is a powerful deep learning architecture designed for understanding and producing human language.  
Unlike earlier models, transformers analyze all words in a sentence simultaneously.

Their key mechanism is **self-attention**, which allows the model to determine how strongly each word relates to others in the sentence.

### Example

Sentence:  
“The dog chased the cat because it was scared.”

A transformer can correctly understand that the word “it” refers to the cat.

Before processing, transformers convert sentences into tokens and then into numerical representations.

### Example Task

Input: "Good morning"  
Output: "Bonjour"

Transformers form the backbone of many modern AI systems, including:
- ChatGPT  
- BERT  
- GPT-4  
- Gemini  
- Claude  

They are highly effective for tasks such as text generation, question answering, reasoning, and even multimodal processing like images and audio.

---

## Tokenization Across Different Language Models

Large language models do not interpret text as complete sentences.  
They first break text into smaller tokens.

### Example

Sentence:  
“Artificial intelligence is powerful.”

Possible tokenization:  
Artificial, intelligence, is, power, ful, .

Different models use different tokenization techniques:

- **GPT Models (OpenAI)** use Byte Pair Encoding (BPE)  
  Example:  
  Internationalization → Intern, ation, al, ization  

- **Google Gemini / T5** use SentencePiece  
  Example:  
  Artificial Intelligence → ▁Artificial, ▁Intel, ligence  

- **Meta LLaMA** uses a multilingual BPE variant  
  Example:  
  Computational → Compute, ation, al  

- **Anthropic Claude** uses an optimized BPE approach  
  Designed for efficiently handling long documents  

- **Chinese, Japanese, and Korean Models** often use character-based tokenization  
  Example (Chinese):  
  我爱你 → 我, 爱, 你  

---

## What Is Parallelism?

Parallelism is the ability to perform multiple operations at the same time instead of executing them sequentially.  
In modern AI systems, especially transformers, parallelism enables the simultaneous processing of many tokens, greatly improving performance.

---

## Real-World Example: Exam Paper Evaluation

Suppose 1,000 exam papers need grading.

### Sequential Method (Traditional)
- One teacher grades all papers alone  
- Papers are evaluated one after another  
- The total process takes a very long time  

### Parallel Method (Efficient)
- The task is divided among 100 teachers  
- Each teacher grades 10 papers at the same time  
- The entire workload finishes much faster  

---

## Parallelism in AI Models

Earlier neural architectures such as RNNs and LSTMs processed sentences word-by-word.  
Each step depended on the previous one, leading to slower training and inference.

---

## Parallel Processing in Transformers

Transformers changed this by enabling all tokens in a sentence to be processed at once.

Example sentence:  
“Artificial intelligence is transforming the world.”

Rather than analyzing words sequentially, transformers examine all tokens simultaneously, allowing better understanding of relationships within the sentence.

This parallel execution makes modern AI systems:
- Faster  
- More scalable  
- Capable of learning from massive datasets  

---

## Conclusion

Parallelism is a key factor behind the efficiency and power of modern Large Language Models such as:
- GPT  
- BERT  
- Claude  
- Gemini  

By combining parallel processing with transformer architecture, these models significantly outperform older sequential approaches in speed, scale, and capability.


# 📅 DAY 3 — Embeddings in Artificial Intelligence

## What Are Embeddings?

- Embeddings are numerical representations of data that capture its meaning and relationships.  
- They convert words, sentences, images, or other data into vectors of numbers so that machines can understand similarities and patterns.

- Instead of treating data as plain text or raw values, embeddings place similar items closer together in a mathematical space.  
- This allows AI systems to compare meaning rather than exact matches.

For example, the words “king” and “queen” will have embeddings that are close to each other, while “king” and “banana” will be far apart.

---

## How Embeddings Work (Conceptually)

When data is converted into embeddings:
- Each item becomes a vector (a list of numbers)
- Similar meanings produce similar vectors
- Different meanings produce distant vectors

These vectors exist in a multi-dimensional space where distance represents similarity.

AI models learn embeddings during training by observing patterns in large datasets.

---

## Example: Word Embeddings

Consider the words:
- dog
- puppy
- cat
- car

The embeddings for “dog” and “puppy” will be very close.  
“Dog” and “cat” will be somewhat close.  
“Dog” and “car” will be far apart.

Even though the model does not understand language like humans, embeddings allow it to recognize semantic relationships.

---

## Example: Sentence Embeddings

Sentence embeddings represent the meaning of an entire sentence.

Examples:
- “How can I reset my password?”
- “I forgot my password, what should I do?”

Even though the words differ, their embeddings will be very similar because the meaning is almost the same.

This allows AI systems to understand intent instead of relying on exact wording.

---

## Example: Image Embeddings

In image-based systems, embeddings represent visual features.

For example:
- Images of dogs will have similar embeddings
- Images of cars will cluster together
- A dog image and a car image will be far apart

This is widely used in face recognition and image search.

---

## Use Cases of Embeddings

- Embeddings are used in semantic search, where results are based on meaning rather than keywords.  
- They power recommendation systems by finding similar users or items.  
- Chatbots use embeddings to match user questions with relevant answers.  
- Embeddings are essential for document clustering and topic grouping.  
- They are used in sentiment analysis to understand emotional tone.  
- Image and video search rely on embeddings to identify similar visual content.  
- Fraud detection systems use embeddings to identify unusual patterns.

---

## Embeddings in Large Language Models

- Large Language Models use embeddings as the first step in understanding text.  
- Input tokens are converted into embeddings before being processed by transformers.  
- Without embeddings, models would not be able to reason about meaning or context.

Embeddings act as the bridge between raw data and intelligent behavior.

---

## Conclusion

- Embeddings transform raw data into meaningful numerical representations that machines can analyze.  
- They allow AI systems to understand similarity, context, and relationships instead of just matching exact values.  
- From search engines to chatbots and recommendation systems, embeddings are a foundational component of modern AI.

In simple terms, **embeddings are how machines convert meaning into numbers**.


# Catalogue Intelligence System Using RAG

## Overview

The Catalogue Intelligence System combines a Catalogue Management System (CMS) with Retrieval-Augmented Generation (RAG) to provide accurate, explainable, and context-aware product insights.  
It is designed to support estimators and designers by transforming raw catalog data into reliable intelligence without hallucinations.

---

## 1️⃣ Data Sources (Real-World Catalog Inputs)

The system ingests multiple types of catalog data commonly used in real-world scenarios:

- PDF-based product catalogs  
- Product images and reference links  
- Technical specifications  
- Pricing information  

These inputs reflect actual data used by estimators and design teams.

---

## 2️⃣ Catalogue Management System (CMS) Ingestion

The CMS ensures data quality, validation, and governance.

### PDF Catalog Processing
- PDF catalogs are processed using OCR tools to extract text  
- Extracted content is manually reviewed and validated  
- SKUs, specifications, and pricing are verified for correctness  

### Price List Processing
- Price data is uploaded through CSV or Excel files  
- Stored as structured records to maintain a single source of truth  

### Images and Product Links
- Product images are stored in object storage  
- Image URLs and product reference links are stored in the database  

All catalog components are linked using a SKU-based reference model.

The CMS ensures clean, trusted, and well-governed data.

---

## 3️⃣ Embedding Generation

After validation, catalog content is prepared for semantic retrieval.

- Text content is split into meaningful chunks  
- Each chunk is converted into embeddings using the MiniLM model  
- Embeddings are stored in MongoDB Vector Search along with metadata:
  - SKU  
  - Tenant ID  
  - Source (PDF page, link, or document)  

This step enables semantic search across the catalog.

---

## 4️⃣ User Query (Live Question)

Example user query:

> “Which LED panels under ₹5,000 are suitable for outdoor use?”

---

## 5️⃣ RAG Workflow (Answer Generation Process)

The system answers queries using a structured RAG pipeline:

- User query is converted into an embedding  
- MongoDB performs vector similarity search  
- Relevant catalog chunks are retrieved  
- The LLM receives:
  - The user question  
  - Retrieved catalog context  

The LLM generates answers strictly based on retrieved data, ensuring factual accuracy.

---

## 6️⃣ Final Output

The system returns a grounded response containing:

- Product name  
- SKU  
- Price  
- Manufacturer or catalog link  

Additional guarantees:
- Full traceability of information sources  
- No hallucination, as the LLM does not invent data  

---

## 7️⃣ System Characteristics

The platform is designed to be:

- Scalable  
- Secure  
- Multi-tenant  

It supports:
- **Estimators** by ensuring cost accuracy  
- **Designers** by enabling efficient product discovery  

---

## 🔄 End-to-End Data Flow

  Websites / PDFs / CSV Files
  
  ↓
  
  Catalogue Management System (Validated & Structured Data)
  
  ↓
  
  Text Chunking → Embeddings
  
  ↓
  
  MongoDB Vector Search
  
  ↓
  
  RAG (Retrieve + Generate)
  
  ↓
  
  Grounded and Explainable Answer


---

## Technology Stack

### Data Storage
- **MongoDB Atlas**
  - Stores structured data (SKU, price, specifications)
  - Supports vector search for embeddings
  - Enables tenant-based data isolation  

- **Object Storage (Local File System)**
  - Stores PDFs and product images
  - MongoDB stores references as URLs  

---

### Ingestion and Processing
- **OCR Tools (Tesseract / Textract)**
  - Extract text from scanned and digital PDFs  

- **Human Validation**
  - Ensures data correctness and trust  

- **CSV / Excel Processing (Pandas)**
  - Handles structured price list ingestion
  - Maintains data integrity  

---

### Embeddings Layer
- **Model:** `sentence-transformers/all-MiniLM-L6-v2`

**Why MiniLM?**
- Open-source and free  
- Lightweight and fast  
- Strong semantic understanding  
- Cost-efficient with 384-dimensional vectors  

**Purpose:**  
Enables semantic search over catalog data.

---

### RAG Orchestration
- **LangChain**
  - Text chunking
  - History-aware query rewriting
  - Prompt orchestration  

- **MongoDB Vector Search**
  - Semantic retrieval
  - Metadata filtering (Tenant ID, SKU)  

---

### LLM for Answer Generation
- **Groq (LLaMA-3)**

Used only for final answer generation:
- Fast inference  
- Low operational cost  
- Converts retrieved context into human-readable responses  

---

### Security and Configuration
- **dotenv**
  - Secure management of API keys and environment variables  

- **Tenant ID Enforcement**
  - Applied during ingestion and retrieval
  - Ensures strict data isolation between tenants  

---

## Summary

This Catalogue Intelligence System uses CMS and RAG to deliver accurate, explainable, and scalable catalog insights.  
By combining validated data, embeddings, vector search, and controlled LLM usage, the system ensures trust, performance, and real-world usability.
