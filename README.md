# GPT-3.5 Summarization with Chain of Density (CoD) ![GPT-3.5](https://img.shields.io/badge/GPT--3.5-Enabled-brightgreen)

This project delves into the capabilities of GPT-3.5 for text summarization, leveraging the concept of Chain of Density (CoD) as proposed in the paper "From Sparse to Dense: GPT-4 Summarization with Chain of Density Prompting". Our aim is to explore how CoD, an advanced method for generating concise summaries, intersects and interacts with the Chain of Thought (CoT) prompting approach, specifically utilizing the OpenAI API.

## :sparkles: Introduction

The concept of Chain of Density (CoD) involves generating dense, information-rich summaries, which can be particularly challenging for AI models. This project is motivated by the goal of understanding how GPT-3.5, with its advanced language capabilities, handles this summarization technique and how it relates to the Chain of Thought (CoT) prompting method. 

## :dart: Objectives

- To apply the CoD approach to GPT-3.5 summarization tasks.
- To analyze the effectiveness of CoD in creating accurate and concise summaries.
- To explore the relationship between CoD and CoT prompting, understanding how they complement or differ from each other.

## :gear: Methodology

- Utilizing the OpenAI API to access GPT-3.5.
- Implementing CoD summarization techniques as per guidelines from the paper.
- Comparing the CoD approach with traditional summarization methods and CoT prompting.
- Analyzing the outputs for quality, accuracy, and density of information.

## :warning: Challenges and Learnings

Throughout the experimentation, all methods were evaluated using test_set.csv. One significant challenge encountered, despite setting the temperature to 0, was the model's unpredictability. Minor prompt modifications, such as altering the sequence of instructions, dramatically impacted the output. For instance, in the extract_entities() function, a prompt stating “extract and rank entities” often led to the model providing not only the entities but also explanations for their rankings. This emphasized the necessity of specifying the exact format of the desired response.

A recurrent issue was the model’s occasional non-compliance with set rules and instructions, observable across various methods. For example, in base_summary(text), even when instructed to “Add a lot of unnecessary connectives between sentences,” the model frequently overlooked this directive. Similarly, in increase_density(), the model often produced summaries exceeding the specified target_length.

Despite these challenges, when tested with test_set.csv, the methods generally performed as expected. The inherent "black-box" nature of the model means that deriving the "best" answer often requires a trial-and-error approach. My findings indicate that the effectiveness of each method is contingent on the provided text; the same prompt can yield varying results depending on the text. However, certain prompt characteristics consistently led to more effective responses:

A. Establishing a relevant system message to define the model's role.

B. Prioritizing more critical instructions, as the model tends to follow earlier instructions more closely.

C. Providing detailed, precise instructions and including exemplary examples only if beneficial.

D. Clearly defining the expected output, including specifics of what should and should not be included in the response.


## :key: Obtaining and Using the OpenAI API Key

### Getting the API Key

1. **Sign Up/Log In:** Visit [OpenAI's website](https://openai.com/) and sign up or log in.
2. **API Access:** Navigate to the API section and apply for API access if you haven’t already.
3. **API Key Generation:** Once access is granted, go to your account dashboard and generate a new API key.

### Setting Up the API Key in Your Project

- **Environment Variable:** Store the API key in an environment variable. This is a security best practice, preventing the key from being hard-coded in your project.
  
  ```bash
  export OPENAI_API_KEY='your-api-key-here'
