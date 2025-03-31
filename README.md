 # AI Language Learning Chatbot 
# Project Summary
This project is an AI-powered chatbot designed to help users learn any language by simulating real-life conversations. It uses OpenAI's GPT-4 models and LangChain to guide users through an immersive, scene-based language practice session.
 # Key Features
1.	Collects user's known and target languages, learning level, and scene context
2.	Runs a multi-step conversation flow in Guide Mode and Practice Mode
3.	Evaluates responses using GPT via structured prompts
4.	Logs both correct and incorrect answers into SQLite
5.	Provides a final feedback summary of common mistakes and improvement suggestions
# Libraries Used
1.	openai, langchain – LLM & memory
2.	dotenv, os – Secure API handling
3.	sqlite3, pandas – Local database and display
4.	tqdm – UI progress enhancement
 # How to Run
1.	Install dependencies:
!pip install openai langchain python-dotenv pandas tqdm
2.	Create a .env file in the root with:
OPENAI_API_KEY=your-api-key-here
3.	Open the notebook and run all cells from top to bottom.
# System Architecture:
![image](https://github.com/user-attachments/assets/a35324ca-bbb4-4fdd-af2a-0590a7c950ee)

 
# User Interaction Flow :
The user runs a single cell that initializes all components: UserProfile, LessonManager, SessionLogger, and LanguageTutor. After providing their details , the tutor session begins. If the user is a Beginner or Intermediate, the session starts in Guide Mode, where commands like next show phrases and help lists available options. Typing switch moves the user into Practice Mode, and start begins the question-answer interaction.
Each user response is evaluated via GPT using LessonManager, with immediate feedback shown. All responses are logged by SessionLogger and saved to a local SQLite database. When the user types exit, the session ends and a personalized feedback summary is generated, highlighting mistakes and suggesting improvements. The user can restart or update their profile by re-running the session.
