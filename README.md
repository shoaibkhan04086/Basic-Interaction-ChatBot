# Basic Interaction Bot

A basic interaction bot using OpenAI GPT-4 to collect user information.

## Prerequisites

- Python 3.6 or higher
- OpenAI Python library
- OpenAI API key

## Setup and Implementation

### Steps to Implement the Bot

1. **Set up the OpenAI API key:**
   - Sign up on the [OpenAI website](https://www.openai.com/).
   - Obtain your API key from the API section of your OpenAI account.
   - Install the OpenAI Python library using pip:
     ```sh
     pip install openai
     ```

2. **Implement the Bot:**
   - Create a Python script (`chatbot.py`) and include the following code:

```python
import openai

# OpenAI API key setup (replace 'your-api-key' with your actual key)
openai.api_key = 'your-api-key'

def chatbot():
    user_data = {}

    # Helper function to ask questions and store responses
    def ask_question(question, key):
        while True:
            print(question)
            response = input().strip()
            if response:
                user_data[key] = response
                break
            else:
                print("Invalid input. Please provide valid information.")
    
    # Greet user and ask for name
    ask_question("Hello! Welcome to our service. May I know your name?", 'name')

    # Ask for email
    ask_question(f"Nice to meet you, {user_data['name']}! Could you please provide your email address?", 'email')

    # Ask for company name
    ask_question("Thank you! Lastly, can you tell me the name of your company?", 'company')

    # Confirm and display stored information
    response = (f"Thanks for the information, {user_data['name']}! Here’s what I’ve got:\n"
                f"Name: {user_data['name']}\nEmail: {user_data['email']}\nCompany: {user_data['company']}\n"
                "Have a great day!")
    print(response)

# Run the chatbot
chatbot()


*Running the Bot*
To run the bot, execute the chatbot.py script in your terminal:"python chatbot.py"

The bot will interact with the user, collect the necessary information, and display the collected data at the end.



