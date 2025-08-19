# Finance Advisor - Personal Finance Assistant

## Overview
Finance Advisor is a Streamlit-based AI-powered finance assistant designed to simplify personal finance management. It enables users to track expenses, access real-time stock information via the Alpha Vantage API, view budget summaries, and receive personalized financial advice through a conversational interface. Powered by LangGraph and the Groq API, Finance Advisor maintains user context across sessions, provides empathetic and clear responses, and includes a Human-in-the-Loop (HITL) mechanism for high-risk queries.<br>

## Features
* **User Profile Collection:** Gathers user details (age, income, goals, risk tolerance) for tailored responses.<br>
* **Real-Time Stock Data:** Fetches stock prices using Alpha Vantage API with robust symbol extraction and error handling.<br>
* **Intent Detection:** Classifies queries into profile updates, stock queries, expense tracking, budget summaries, or advice.<br>
* **Memory Management:**<br>
    Short-term memory for in-session context (e.g., previous intents).<br>
    Long-term memory for cross-session continuity (e.g., past advice).<br>
* **Human-in-the-Loop (HITL):** Flags high-risk queries (e.g., "liquidate retirement account") for simulated human review.<br>
* **Empathetic Responses:** Uses clear, jargon-free language for users with limited financial literacy.<br>
* **Debugging:** Includes logging to troubleshoot API issues.<br>

## Prerequisites
* **Python:** Version 3.8 or higher.<br>
* **Virtual Environment:** Recommended to isolate dependencies.<br>
* **API Keys:**<br>
    Groq API key (for LLM).<br>
    Alpha Vantage API key (for stock data).<br>

## Setup Instructions
* **Clone the Repository (if applicable):**<br>
    git clone https://github.com/vishwajeetsingh01/finance_advisor_using_langgraph.git<br>
    cd finance_advisor_using_langgraph
* **Create Virtual Environment:**<br>
    Create a virtual environment named venv.<br>
    python3 -m venv venv<br>
* **Activate Virtual Environment:**<br>
    On macOS/Linux: source venv/bin/activate<br>
    On Windows: venv\Scripts\activate<br>

* **Install Dependencies:**<br>
    Install required packages from requirements.txt.<br>
    pip install -r requirements.txt<br>

* Contents of requirements.txt<br>
    streamlit>=1.30.0<br>
    langchain>=0.1.14<br>
    langchain_groq>=0.1.4<br>
    langgraph>=0.0.35<br>
    python-dotenv>=1.0.0<br>
    requests>=2.31.0<br>

* **Set Up Environment Variables:**<br>
    Create a .env file in the project root with your API keys.<br>
    GROQ_API_KEY=<your-groq-api-key><br>
    ALPHA_VANTAGE_API_KEY=<your-alpha-vantage-api-key><br>

* **Run the Application:**<br>
    Start the Streamlit app.<br>
    streamlit run app.py<br>

* Access the app at http://localhost:8501 in your browser.<br>

![alt text](assets/image.jpg)

* Deactivate Virtual Environment (when done).
    deactivate

## Usage
* **Interface:** <br>
    Use the chat-based UI to:<br>
    Check stock prices (e.g., "What’s the price of AAPL stock?").<br>
    Track expenses (e.g., "Add $50 for groceries").<br>
    Request budget summaries (e.g., "Show my budget").<br>
    Seek financial advice (e.g., "How should I save for a house?").<br>
    Share profile details (e.g., "I’m 30 and earn $50,000").<br>

* **Example Prompt:**<br>
What’s a good budget plan for someone my age who earns $50,000 a year and wants to save for a car?<br>
* **High-Risk Queries:**<br>
Queries like "Should I liquidate my retirement account?" trigger a simulated HITL response.<br>

## Project Structure
finance_advisor_using_langgraph/<br>
├── venv/                   # Virtual environment directory<br>
├── .env                    # Environment variables (API keys)<br>
├── .gitignore              # Excludes venv/, .env<br>
├── app.py                  # Main Streamlit application<br>
├── README.md               # Project overview and setup<br>
└── requirements.txt        # Python dependencies<br>

* **Notes:**<br>
* **Stock Data:** Uses Alpha Vantage API for real-time stock prices. Free tier limits to 5 calls/minute; monitor usage or upgrade for higher limits.<br>
* **Debugging:** Check terminal logs for API response details or errors (e.g., rate limits, invalid symbols).<br>
* **Security:** Store API keys in .env to avoid hardcoding.<br>
* **Troubleshooting:**<br>
&nbsp;Verify API keys in .env.<br>
&nbsp;Ensure internet connectivity for Alpha Vantage API.<br>
* Upgrade pip if dependency issues arise: python -m pip install --upgrade pip.<br>