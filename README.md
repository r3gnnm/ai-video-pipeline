# 🎬 AI Video Content Pipeline
End-to-end pipeline for text-to-video generation with automatic 
prompt optimization using Runway ML + LLM feedback loop.

## How it works
1. Text topic → LLM generates video prompt (3 strategies)
2. Runway ML Gen-3 generates video
3. Quality evaluation: CLIP score + motion + sharpness
4. If quality < threshold → LLM rewrites prompt → repeat

## Results
Auto-improvement loop: **+18% quality gain per iteration**
| Strategy | CLIP | Motion | Sharpness | Overall |
|---|---|---|---|---|
| chain-of-thought | 0.71 | 0.68 | 0.74 | 0.71 |
| storytelling | 0.68 | 0.65 | 0.70 | 0.68 |
| descriptive | 0.65 | 0.60 | 0.71 | 0.65 |

## Stack
Python · Runway ML Gen-3 · OpenAI GPT-4o-mini · CLIP · OpenCV · pandas

## Setup
1. Get API keys: [Runway ML](https://runway.ml) and [OpenAI](https://platform.openai.com)
2. Add to Colab Secrets: `OPENAI_API_KEY` and `RUNWAY_API_KEY`
3. Open `notebooks/video_pipeline.ipynb` in Google Colab
4. Run all cells
