# 🧾 Invoice Analyzer with Flowise + Groq + LLaMA 3

This is a visual AI pipeline built using **Flowise**, powered by **Groq's lightning-fast LLaMA 3 70B**, to extract structured data like invoice number, customer ID, and total amount from uploaded PDFs.

---

## ⚙️ Tech Stack
- **Flowise** (Low-code visual Langchain builder)
- **Groq API** (Running LLaMA 3.3 70B Versatile)
- **Langchain** (PromptTemplate, LLMChain, StructuredOutputParser)
- **Docker** (optional, for deployment)
- **Node.js** (required to run Flowise locally)

---

## 🔧 Flowise Tools Used

1. **GroqChat**  
   - Credential: `groq` (Groq API key)
   - Model: `llama-3-3-70b-versatile`
   - Temperature: `0.6`

2. **Prompt Template**
   - Template:
     ```
     Extract the following information from the provided invoice

     -Invoice Number
     -Customer Number
     -Gross Amount including VAT

     INVOICE CONTENT:
     {invoice}
     ```
   - Format Prompt Values: file attachment selected as input

3. **LLM Chain**
   - Language Model: connected to GroqChat
   - Prompt: connected to Prompt Template
   - Output Parser: connected to Structured Output Parser

4. **Structured Output Parser**
   - Autofix: Enabled

---

## 🧪 How It Works

📤 **You upload a PDF invoice**

🧠 **The text is inserted into a formatted prompt**

📨 **Prompt is sent to LLaMA 3 via Groq API**

📦 **Model returns a JSON structure with extracted fields**

🧾 **Final output includes Invoice Number, Customer Number, and Gross Amount**

---

## 🚀 How to Use (Local or EC2)

### ✅ Run Locally
1. Install Flowise globally:
   ```bash
   npm install -g flowise
