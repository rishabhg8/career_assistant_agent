---
title: career_conversation
app_file: app.py
sdk: gradio
sdk_version: 6.19.0
---
# AI Portfolio Assistant

**An intelligent chatbot that represents you on your personal website, powered by OpenAI's GPT-4o-mini.**

🚀 **[Try it now](https://huggingface.co/spaces/rishabhg7/career_conversation)**

## What is this?

This is an AI agent that answers questions about your professional background, skills, and experience on behalf of you. It uses your LinkedIn profile and summary as context to provide authentic, knowledgeable responses to website visitors. When the chatbot encounters unknown questions or interested visitors, it automatically records these interactions for your follow-up.

## Quick Start

### Installation

```bash
uv sync
```

### Running the App

```bash
uv run gradio deploy
```

The chatbot interface will launch and be accessible via Gradio. It's ready to deploy on Gradio Spaces or run locally.

## How It Works

The chatbot uses:
- **Your Profile Data**: LinkedIn PDF + summary text file for context
- **OpenAI GPT-4o-mini**: Intelligent language model for responses
- **Tool Calling**: Records user emails, names, and unknown questions for follow-up
- **Pushover Notifications**: Alerts you in real-time when actions occur

## Usage Example

A visitor asks: *"What are your main technical skills?"*

The chatbot:
1. Reads your LinkedIn profile and summary from the context
2. Generates a response based on your actual experience
3. Returns a professional, personalized answer

## Setup Requirements

Before running, ensure you have:

1. **OpenAI API Key** - Set as environment variable `OPENAI_API_KEY`
2. **Pushover Credentials** (optional, for notifications):
   - `PUSHOVER_TOKEN` - Your app token
   - `PUSHOVER_USER` - Your user key
3. **Profile Files** in `me/` directory:
   - `linkedin.pdf` - Exported LinkedIn profile
   - `summary.txt` - Brief professional summary

## Key Features

### Tools

The assistant has two built-in tools:

- **`record_user_details`** - Captures visitor email, name, and conversation notes
- **`record_unknown_question`** - Logs questions the chatbot couldn't answer

### Notifications

Uses Pushover to send real-time notifications when:
- A new lead provides contact information
- An unanswered question is received

## File Structure

```
├── app.py              # Main application
├── uv                  # Dependencies
├── me/
│   ├── linkedin.pdf    # Your LinkedIn profile
│   └── summary.txt     # Professional summary
└── README.md          # This file
```

## Configuration

Update these fields in the `Me` class to personalize:
- `self.name` - Your full name
- Path to your LinkedIn PDF
- Path to your summary file

## License

MIT
