# Web Scraping Agent

A Python-based web scraping agent that combines Playwright browser automation with OpenAI's structured output capabilities to extract and parse course information from websites.

<div align="center">
  <img src="screenshot.png" alt="Web Scraping Agent in action" width="800"/>
  <p><em>Web Scraping Agent extracting course data from deeplearning.ai</em></p>
</div>

## Features

- Automated web scraping using Playwright
- AI-powered content extraction with OpenAI GPT-4
- Structured data output using Pydantic models
- Screenshot capture for visual verification
- Interactive Jupyter notebook interface
- Configurable filtering and targeting of specific content

## Requirements

- Python 3.12+
- OpenAI API key

## Installation

1. Clone the repository and navigate to the project directory

2. Create a virtual environment:
```bash
uv venv --python=3.12
```

3. Activate the virtual environment and install dependencies:
```bash
# Activate the environment (platform-specific)
uv pip install -r requirements.txt
```

4. Install Playwright browsers:
```bash
playwright install
```

5. Set up environment variables:
```bash
cp .env.example .env
# Edit .env and add your OpenAI API key
```

## Usage

The main functionality is contained in the Jupyter notebook `web_scraping_agent.ipynb`. The agent can:

1. **Scrape all courses** from a target website
2. **Filter specific courses** based on subject matter or other criteria
3. **Generate structured output** with course details including title, description, presenter, image URL, course URL, and duration
4. **Capture screenshots** for visual verification of the scraped content

### Example Usage

```python
# Scrape all courses
target_url = "https://www.deeplearning.ai/courses"
instructions = "Get all the courses"
result, screenshot = await webscraper(target_url, instructions)

# Filter specific courses
subject = "Model Context Protocol (MCP)"
instructions = f"Read the description of the courses and only provide all the courses that are about {subject}."
result, screenshot = await webscraper(target_url, instructions)
```

## Project Structure

- `web_scraping_agent.ipynb` - Main notebook with scraping logic
- `helper.py` - Utility functions for environment setup and visualization
- `requirements.txt` - Python dependencies
- `.env.example` - Environment variables template

## Key Components

- **WebScraperAgent**: Handles browser automation and content extraction
- **DeeplearningCourse**: Pydantic model for structured course data
- **AI Processing**: Uses OpenAI's structured output for intelligent content parsing
- **Visualization**: HTML table generation with embedded images and links

## References

Based on concepts from DeepLearning.ai: [Building AI Browser Agents](https://www.deeplearning.ai/short-courses/building-ai-browser-agents/)