### Installation
```bash
python3 -m venv venv
pip install -r requirements.txt
```
Additionally you need to install [ollama](https://ollama.com/download) on your machine and make sure you pull the following models,
```bash
ollama --version
ollama pull mistral:instruct
ollama pull llama2:latest
```

#### Interact with a PDF
This is based on `chainlit` UI. 
```bash
chainlit run chainlit_pdf.py -w
```

#### Interact with CSV
This is based on `Streamlit` UI.
```bash
streamlit run streamlit_csv.py
```

#### Comments
* Currently the implementation is more around being able to interact with documents/CSV 
* For more enhanced RAG, we need the ability to create a feedback loop around these RAG systems by the way of using C-RAG (Corrective RAG) which is something that Langchain's langraph can help achieving (yet to be made available generally) More on this here https://www.youtube.com/watch?v=OnQQeWEwzyw

### Proposed Solution
* Data Bank that has sub folders for CSVs/CVs/Images etc
* An induction document which contains a questionaire about how the person thinks, so that it helps in giving the bot a kickstart on how to manage responses whenever starting a convo. This needs to be fed anytime a chabot instance comes to life. 
* The bot can then respond to queries and the client can use prompts OR feedback to showcase whther the responses are better or not. Using Langgraph's new feedback tool, this could be fed back to the bot and made more aware of the user under question.