# Project Setup and Execution

This document outlines the steps required to set up and run the project, including API key configuration, environment setup, and running both the backend and frontend components.

## API Keys and Configuration

Sensitive API keys and configuration details are managed securely and accessed as environment variables.  A template file, `apikey.py`, is provided for you to populate with your actual keys.  **Do not commit this file to version control.**

The following keys are required:

1. **TMDB API Key:** Used to interact with the TMDB API for fetching movie data (genres, popular movies, etc.).  Obtain your key from [https://www.themoviedb.org/signup](https://www.themoviedb.org/signup).

2. **MongoDB Connection String:** Connects the application to the MongoDB Atlas database for storing movie metadata, embeddings, and user query history.  Create a MongoDB Atlas account and database at [https://www.mongodb.com/atlas](https://www.mongodb.com/atlas).

3. **Groq Cloud API Key:** Used for integration with the Groq Cloud API to call the `llama-3.3-70b-versatile` Large Language Model (LLM) for generating personalized recommendations. Obtain your key from [https://console.groq.com/keys](https://console.groq.com/keys).

### `apikey.py` Template

Populate the `apikey.py` file with your actual keys.  **Again, do not commit this file to version control.**  An example is shown below:

```python
TMDB_API_KEY = "your_tmdb_api_key_here"
MONGO_CONNECTION_STRING = "your_mongo_connection_string_here"
GROQ_API_KEY = "your_groq_api_key_here"
```

## How to Run the Application

### Backend

1. **Set Up Virtual Environment**:

   ```bash
   cd backend
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   export GROQ_API_KEY=<your_groq_api_key_here>
   ```

2. **Install Dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

3. **Run the Backend Server**:

   ```bash
   python app.py
   ```

   The backend will run at `http://0.0.0.0:5001`.

---

### Frontend

1. **Navigate to the Frontend Directory**:

   ```bash
   cd my-rag-frontend
   ```

2. **Install Dependencies**:

   ```bash
   npm install
   ```

3. **Start the Development Server**:

   ```bash
   npm run dev
   ```

   The frontend will run at `http://localhost:3000`.

---
