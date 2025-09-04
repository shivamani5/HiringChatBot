# HiringChatBot
Chat Bot for Hiring Assistance


 AI Hiring Assistant
An interactive AI-powered technical interview application built with Streamlit. This assistant collects candidate information, generates technical questions based on skillset and experience, evaluates answers using AI, provides real-time feedback, and maintains a leaderboard.

=>Features
Candidate data collection

Dynamic question generation based on role & skills

AI-based evaluation and feedback

Score tracking and leaderboard

=> Requirements
Python 3.8+

Streamlit

Hugging Face Transformers (or any model backend used in get_feedback)

SQLite (for local database storage)

Install dependencies with:

bash
Copy
Edit
pip install streamlit pandas sqlite3 openai
Also, ensure the following modules are available (either custom or third-party):

prompt.py

questions_generator.py

feed_back.py

database.py

table_fields.py

=> Project Structure
pgsql
Copy
Edit
> ai-hiring-assistant/
├── app.py
├── prompt.py
├── questions_generator.py
├── feed_back.py
├── database.py
├── table_fields.py
└── README.md
=> Running the App
bash
Copy
Edit
streamlit run app.py
=> Step-by-Step Usage
1. Introduction Screen
A chatbot image and a welcome message are shown.

Click Start to begin the interview process.

2. Candidate Information
Fill in your name, email, phone number, and location.

The app checks if the user already exists in the database. If yes, a warning is shown.

3. Skill & Role Details
Enter your Role, Years of Experience, and Tech Stack (comma-separated).

Click Generate to create customized questions.

4. Answering Questions
The app displays questions based on the given role and skills.

You input answers and submit them.

The app calls get_feedback() for each question to provide feedback and score.

5. View Feedback & Score
Once submitted, feedback is shown next to each answer.

Average score is calculated and displayed.

6. Leaderboard
After ending the chat, your performance is stored.

The app displays the top scores by skill and candidate.

=> AI Model Usage
The feedback mechanism (get_feedback) likely uses a large language model (LLM) such as OpenAI or a Hugging Face model. Make sure to configure this accordingly in feed_back.py.

=> Database
SQLite is used to:

Store candidate info

Track scores per skill

Maintain leaderboard

Make sure the following tables are created in your database:

users

scores (or similar, based on insert_score() and get_leaderboard())

=> Session Management
st.session_state is used to track:

Candidate details

Interview stage

Skill inputs

Questions/answers/feedback

Scores (Fetches the top 10 candidates from the databse)
