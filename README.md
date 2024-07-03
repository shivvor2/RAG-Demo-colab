(Note: this works as intended but not as well as I thought)
TODO: 
- Try different embedding models
- Try changing the place where the context is inserted

# RAG-Demo-colab
RAG demo using Langchain.
For the documents to be retrieved from, we first 
1. Seperate each documents into chunks
2. Get an embedding from each chunk and store them in a vector Database
When performing inference, we retrieve (huge caveat) the most relevant chunks from the vector DB and then just plug them into the context

# How is it different from youtube tutorials

Instead of using the whole chat history as a query, we use the LLM to generate a query statement and then use it to query the vector database instead.

In a multiround conversation context, this should prevent the chat history from "contaminating" the query vector, with the cost of having to perform double the inference (one time to generate the query statement and one time to generate the actural response).


