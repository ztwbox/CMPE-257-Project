Project Proposal: Graph-Enhanced Retrieval-Augmented Generation for Multi-Hop Question Answering
Problem Description
In recent years, large language models (LLMs) have been able to answer many questions by learning from vast amounts of data. However, their responses may sometimes be outdated or insufficiently personalized. Retrieval-Augmented Generation (RAG) has emerged as an effective method for addressing these limitations. RAG retrieves relevant information from a vector or graph database and provides it to an LLM to generate an evidence-based answer.
Traditional RAG systems typically retrieve information based on vector similarity scores. Although this approach performs well for simple factual questions, it can be less effective when answers require information from multiple sources. Traditional vector search does not explicitly model the relationships among different pieces of information.
The research paper I selected introduces an enhanced graph-based RAG method called HippoRAG 2. HippoRAG 2 converts the context of documents into a knowledge graph inspired by the neurobiology of human memory. The goal of this project is to investigate whether HippoRAG 2 can improve question-answering performance across three dimensions: factual memory, sense-making, and associativity. This project could benefit LLM-based applications such as customer service systems, student assistants, and research assistants.
Dataset
Research Paper Link:
From RAG to Memory: Non-Parametric Continual Learning for Large Language Models
Code/Data Link:
HippoRAG GitHub repository
QA Dataset
Unlike traditional classification or regression model training, this project focuses on question-answering and information-retrieval tasks. There are two types of question-answering datasets. Simple QA is used to evaluate the model’s ability to accurately recall and retrieve factual knowledge. Multi-hop QA is used to measure the associativity of the knowledge graph created by HippoRAG 2.Discourse understanding QA evaluates sense-making by testing the capability to interpret and reason over lengthy, complex narratives.
Implementing all seven datasets used in the original paper would be too extensive for this project. Therefore, I decided to select one dataset for each category, Natural Questions, for simple QA and two datasets, MuSiQue, for multi-hop QA and NarrativeQA for Long-context
sense-making. Each dataset generally contains three components: questions, passages or long
answers, and short answers. The questions and their corresponding short answers will be used
to evaluate the model, while the passages will be used to construct the enhanced graph-based
RAG system.
Initial Approach
The experiment will compare three retrieval methods: a simple baseline, a large embedding
model, and a structure-augmented RAG system. BM25 will be used as the simple baseline,
GTE-Qwen2-7B-Instruct as the large embedding model, and GraphRAG and HippoRAG 2 as
structure-augmented RAG methods. Performance will be evaluated using two metrics: Passage
Recall@5 and Answer F1 score.
Recall@5:It divides the number of relevant items found in the top 5 spots by the total number of
relevant items that exist for that query.
F1-score:a single performance metric that combines a classification model's precision
and recall using their harmonic mean
Expected Challenges
1. The original paper uses Llama-3.3-70B-Instruct for extraction and triple filtering and
NV-Embed-v2 as the retriever.Running a 70B model locally would be impractical for
many student projects. I may use a smaller/open-source model such as Qwen 2.5.
2. The original paper evaluates seven datasets and many different retrieval systems.
Reproducing the complete experiment would be too large for a semester project. Thus, I
will focus on MuSiQue as the primary dataset and only pick 500-1000 questions
depending on computational resources.
Team Role
This is an individual project. I will be solely responsible for all phases of the project, including
environment setup, data preprocessing, graph construction, running the experimental baselines,
evaluating results, and compiling the final report.
