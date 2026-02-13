# Voice-Guided Health Assistant
Powered by Llama 3.3 70B

## Overview

Voice-Guided Health Assistant is a web application that allows users to ask general health-related questions, describe symptoms, or upload medical documents (PDFs, images, text files). It delivers plain-language explanations and structured responses while automatically speaking a concise summary of the key points using the browser's built-in Web Speech API. The application is strictly informational and includes prominent reminders that it is not a substitute for professional medical advice.

## Core Features

- Multiple interaction modes: general health chat, symptom analysis, document interpretation, medication information, medical report explanation
- File upload support for PDFs, images (PNG/JPG), and plain text documents
- Automatic text-to-speech of a shortened, natural summary after each response
- Full detailed answer always visible on screen (including multi-specialist style breakdowns when applicable)
- Browser-native speech synthesis (no external TTS service required)
- Conversation history preserved during the session
- Export chat and clear history options

## Technology Stack

- Frontend: HTML, CSS (custom responsive design), vanilla JavaScript
- Backend LLM: Meta Llama 3.3 70B Instruct (routed via Groq through Hugging Face inference endpoint)
- Speech: Web Speech API (SpeechSynthesisUtterance)
- File handling: FileReader API (data URL for images, text content for others)

## Important Disclaimers

This application is a personal technology demonstration only.

It is not a medical device, not certified for clinical use, and not intended to provide medical diagnosis, treatment recommendations, or replace consultation with a licensed healthcare professional.

All responses include explicit warnings to seek qualified medical advice for any health concern.

The author assumes no liability for any decisions made based on the output of this tool.

## Setup and Local Usage

1. Clone the repository
git clone https://github.com/yourusername/voice-guided-health-assistant.git
text2. Open `index.html` directly in a modern browser (Chrome, Edge, or Firefox recommended for best speech support)

No build step or server is required.

## API Configuration

The application uses a Hugging Face inference endpoint with Groq routing.

Replace the `HF_TOKEN` constant in the `<script>` section with your own Hugging Face API token that has access to the Llama 3.3 70B model via Groq.

```javascript
const HF_TOKEN = 'hf_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx';
Limitations

Speech synthesis quality and availability depend on the user's browser and operating system
Very long responses are intentionally shortened for spoken output to maintain listenability
Image analysis is limited to models that accept base64 data URLs
No persistent storage — conversation resets on page refresh
Rate limits and costs apply when using the Hugging Face / Groq inference API

License
MIT License
See the LICENSE file for details.
