### LLM Google Gemini AI 

- API Key - https://makersuite.google.com/app/apikey

- Tutorials - https://ai.google.dev/tutorials/python_quickstart

- colab - https://colab.research.google.com/github/google/generative-ai-docs/blob/main/site/en/tutorials/python_quickstart.ipynb


### project setup
```bash
!pip install streamlit
!pip install google-generativeai
!pip install python-dotenv

conda create -p aienv python==3.11.4
conda activate aienv/
pip install -r requirements.txt

# GOOGLE_API_KEY=""
```

###  API verification 
```bash
import os
os.environ["GOOGLE_API_KEY"] = ""
genai.configure(api_key=os.environ["GOOGLE_API_KEY"])
for m in genai.list_models():
  if 'generateContent' in m.supported_generation_methods:
    print(m.name)

## python main.py
#  models/gemini-pro
#  models/gemini-pro-vision

```

### generate text
```bash
model = genai.GenerativeModel('gemini-pro')
response = model.generate_content("What is the GDP of USA?")
print(response.text)
# As of 2023, the GDP of the United States is estimated to be around $25.3 trillion, making it the largest economy in the world.
```