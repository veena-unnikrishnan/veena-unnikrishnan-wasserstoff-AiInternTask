# AI INTERN TASK

# AI Personal Email Assistant (Beginner to Intermediate Level)

# Objective:

Build an AI-powered personal email assistant capable of reading a user's Gmail/IMAP inbox, understanding email context, storing emails in a database, and interacting with external tools (web search, Slack, calendar) to assist with email actions. The assistant should be able to automatically draft or send replies, forward information, and schedule events based on email content.

# Detailed Requirements:

● Email Integration: Authenticate to Gmail (or any IMAP email service) using OAuth2 (or secure SMTP/IMAP credentials). Fetch emails from the inbox (and possibly sent items) via a Python script. Leverage the Gmail API (preferred) or IMAP protocols to read emails programmatically (the Gmail API is a RESTful interface allowing Python scripts to interact with Gmail.

● Parsing and Storage: Parse essential email fields (sender, recipient, subject, timestamp, body, attachments) and store this data in a database (e.g. PostgreSQL, SQLite). This database will serve as a knowledge base for the assistant, enabling it to retrieve conversation history or prior context for a given thread. Ensure proper schema design for threading (linking replies to original emails).

● Context Understanding with LLM: Use a Transformer-based large language model (OpenAI GPT-3.5/4 via API, or a HuggingFace model) to interpret the email’s content and intent. For example, the model should summarize long email threads or infer the sender’s request. This may involve prompt engineering to provide the model with relevant email context (such as the latest emails in a thread) and asking for an outcome (e.g. a draft reply or action plan).

● Tool Integration – Web Search: Integrate a web search capability (e.g. using an API like Google Custom Search or Bing API) that the assistant can use when an email asks a question or requests information not in the email. The assistant might decide to query the web for an answer and include the results in its reply. Document how the search results are retrieved and filtered for relevance.

● Tool Integration – Slack: Integrate Slack’s API to forward messages or notifications. For instance, if an important email arrives, the assistant could send a Slack message to a specified workspace/channel/user with the email content. Use Slack Web API (e.g. chat.postMessage) with a bot token to send messages. Ensure the OAuth scope for Slack bot permits posting messages.

● Tool Integration – Calendar: Incorporate calendar scheduling by using the Google Calendar API (or a dummy scheduling function). The assistant should identify if an email is about meeting scheduling (e.g. detects phrases like "meeting on Friday") and then interact with the calendar to create an event or to propose times. This could be done by prompting the LLM to output a structured request (e.g. date, time, title of meeting) that your code uses to call the Calendar API.

● Automated Reply Generation: In cases where the assistant can handle the email, have it draft a reply. For example, if an email asks to schedule a meeting, the assistant can draft a polite response proposing a time (after booking on calendar). Leverage the LLM to generate the email text, then send it via SMTP or Gmail API. Ensure safeguards: perhaps only auto-send replies for certain simple cases, and log or require confirmation for others to avoid mistakes.

● Documentation of Process: Document all major steps, design decisions, and assumptions. This includes how emails are fetched and stored, how the LLM is prompted, what tools are integrated and how, and how the overall flow is orchestrated. If you encounter challenges (e.g., authentication issues, rate limits, LLM output formatting problems), record how you solved them.

● Use of AI Coding Assistants: You are encouraged to use AI coding tools like Cursor or GitHub Copilot to assist in development. If you do, capture the interaction transcript or a summary of how the AI helped (this could be included in the documentation). This will provide insight into how AI can boost developer productivity.


# Deliverables:

● Working Prototype: A running demo of the email assistant (can be a command-line script or simple web interface) showing it reading an inbox and performing actions (like replying or sending a Slack message).

● Code Repository: A GitHub repository containing all source code. Follow a clean project structure (e.g. separate modules for email fetching, LLM logic, tool integrations, and utils). For example: src/ with subfolders like controllers/ (orchestrating flows), services/ (for external service APIs like Gmail/Slack), utils/ (helper functions), etc. Include a requirements.txt or environment.yaml for dependencies.

● Technical Documentation: A README.md explaining the project. Include instructions to set up any API credentials (Gmail, Slack, etc.), how to run the assistant, and examples of usage. Also include an architecture diagram outlining components (you can use simple tools or draw.io to illustrate how the email, LLM, and tools interact). Describe the overall architecture in words as well, mentioning how data flows from the inbox to the LLM to the actions.

● Video Walkthrough: A short video (screen recording) demonstrating the assistant in action. For example, show the terminal or interface as it checks email, invokes the AI to draft a reply, and sends out a Slack notification or calendar invite. This helps in evaluating the solution end-to-end.
