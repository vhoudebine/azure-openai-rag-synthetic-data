# README  
   
This repository contains a Python notebook that demonstrates the use of Azure OpenAI to generate synthetic question-answer pairs from a PDF document in order to create labelled evaluation data for a Retrieval Augmented Generation application. 
   
## Contents  
- `synthetic_rag_evaluation_data.ipynb`: The primary notebook that guides you through the following steps:  
  1. Preparing source documents: Load a PDF document and split it into manageable chunks.  
  2. Setting up an Azure OpenAI agent: Configure the Azure OpenAI API for question-answer generation.  
  3. Generating an evaluation dataset with Q&A pairs: Use the Azure OpenAI agent to generate question-answer pairs from the document chunks.  
  4. Saving the evaluation dataset as jsonl: Store the generated Q&A pairs in a JSON Lines file.  
  5. Writing documents to Azure AI Search: Index the document chunks using Azure AI Search for later retrieval.  
  6. Testing the Azure AI Search index: Perform hybrid search queries on the indexed data.  
   
### Dependencies  
- Python 3.11  
- Required packages: `langchain`, `openai`, `dotenv`, `azure-search-documents`, `tqdm`, `pandas`  
   
### Instructions  
1. Clone the repository and navigate to the project directory.  
2. Install the required Python packages:  
   ```bash  
   pip install -r requirements.txt  
   ```  
3. Create a `.env` file in the project root directory and add your Azure OpenAI and Azure Search credentials:  
   ```bash  
   AZURE_OPENAI_API_KEY=<your-openai-api-key>  
   AZURE_OPENAI_ENDPOINT=<your-openai-endpoint>  
   AZURE_SEARCH_ENDPOINT=<your-search-endpoint>  
   AZURE_SEARCH_ADMIN_KEY=<your-search-admin-key>  
   ```  
4. Execute the notebook using Jupyter Notebook:  
   ```bash  
   jupyter notebook synthetic_rag_evaluation_data.ipynb  
   ```  
5. Follow the steps described in the notebook to prepare the data, generate Q&A pairs, and index the data in Azure Search.  
   
### Output  
- The generated Q&A pairs will be saved in the `qa_couples.jsonl` file.  
- The indexed data will be stored in the specified Azure Search index, making it available for search queries.  
   
### Notes  
- Ensure the Azure OpenAI and Azure Search services are properly configured with the required permissions.  
- The notebook uses a sample PDF document (`r1t-owner-guide.pdf`). You can replace this with your own document to generate synthetic Q&A pairs.