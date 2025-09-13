# 🔬 HEA Query

**LLM-Powered Research Assistant for High Entropy Alloys**  
*Hackathon: LLM for Materials Science*

---

## 🧠 Summary

**HEA Query** is a research assistant built to enable intelligent access to both unstructured scientific literature and structured datasets related to **High Entropy Alloys (HEAs).**

We combine:

- 🔍 A semantic search engine over thousands of research paper chunks  
- 📊 Cleaned and normalized tabular datasets containing alloy properties  
- 🤖 A powerful LLM (Mistral-7B) to generate natural language answers  
- 🖥️ An interactive Gradio interface for easy exploration

This assistant helps materials scientists ask questions like:

> 🧪 _"Which FCC alloys have Vickers hardness above 200?"_  
> 📈 _"Show me alloys with high entropy mixing and low modulus."_  
> 📚 _"What do recent papers say about yield strength trends in BCC HEAs?"_

---

## 🚀 Features

- 🔍 **Semantic paper search** using FAISS + BAAI embeddings  
- 📊 **Smart dataset filtering** using canonical and synonymous property names  
- 🤖 **LLM-based reasoning** via Mistral-7B  
- 🧾 **Unified prompt generation** from papers + structured data  
- 🖥️ **Gradio app** with answer + tables + raw paper context

---

## 📂 Resources Used

### 📚 Resource 1: Literature Corpus

- ~3000 open-access PDFs on HEAs
- Extracted sections: `abstract`, `introduction`, `methods`, `conclusion`
- Chunked with LangChain `RecursiveCharacterTextSplitter`
- Embedded with `BAAI/bge-base-en`
- Indexed using `FAISS`

### 📊 Resource 2: Structured Datasets

| Dataset   | Description                                | Format              |
|-----------|--------------------------------------------|---------------------|
| MPEA      | Experimental data (HV, UTS, density, etc.) | `dataset1_clean.csv` |
| ML Pred   | Design parameters + predictions            | `dataset2_clean.csv` |
| Achief    | Thermodynamic + phase data                 | `dataset3_clean.csv` |

➡️ Each dataset was cleaned, normalized, and reformatted for query integration.

---

## 🧠 Model Details

- **LLM**: `Mistral-7B-Instruct v0.3`
- **Embeddings**: `BAAI/bge-base-en`
- **Frameworks**: LangChain, Transformers, FAISS, Gradio

---

## 💬 How It Works

1. User submits a question.
2. The system:
   - Uses **FAISS** to retrieve relevant paper chunks.
   - Filters HEA datasets based on numeric or categorical queries.
   - Constructs a unified prompt combining both results.
3. **Mistral LLM** generates a structured, domain-aware response.

### Outputs:
- 📄 **LLM Answer**
- 📊 **Matching rows from datasets**
- 📚 **Raw context from papers**

---

## 🖥️ Gradio Demo UI

| Panel         | Description                                 |
|---------------|---------------------------------------------|
| 🧠 LLM Answer | Natural language response from Mistral      |
| 📊 CSV Matches | Tabular results matching query filters      |
| 📚 FAISS Context | Raw text from relevant research papers      |

---

## 🧑‍💻 Team

- **Taradutt Pattnaik** – [University of Connecticut, Storrs]  
- **Sanjeev K Nayak** – [University of Connecticut, Storrs]  
- **Alexander Horvath** – [University of Connecticut, Storrs]  

---

## 📚 Dataset References _(to be added)_

- [1] MPEA Dataset – *C. Borg, “Expanded dataset of mechanical properties and observed phases of multi-principal element alloys”. figshare, 12-Jul-2020, doi: 10.6084/m9.figshare.12642953.v9* 
- [2] ML Pred Dataset – *R. Machaka, G. T. Motsi, L. M. Raganya, P. M. Radingoana, and S. Chikosha, “Machine learning-based prediction of phases in high-entropy alloys: A data article,” Data in Brief, vol. 38, p. 107346, Oct. 2021, doi: https://doi.org/10.1016/j.dib.2021.107346.*
- [3] Achief Dataset – *C. E. Precker, A. Gregores Cotoand S. Muíños Landín, “Materials for Design Open Repository. High Entropy Alloys”. Zenodo, Aug. 03, 2021. doi: 10.5281/zenodo.5155150.*  

---

