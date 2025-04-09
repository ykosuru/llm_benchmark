This is a framework for evaluating Large Language Models (LLMs) on code generation tasks. It provides standardized benchmarks with flexible configurations, and robust evaluation metrics to assess model performance across different programming challenges.

Overview
OpenCodeEval is a robust framework designed to evaluate LLMs' performance on code generation tasks. It supports multiple benchmark datasets and provides flexible evaluation configurations.

Features
Multiple benchmark dataset support:

HumanEval & HumanEvalPlus
MBPP & MBPP+
LeetCode
Flexible model support:

Base models
Chat models
Backend support:

vLLM acceleration
OpenAI API integration (coming soon)
Comprehensive evaluation tools:

Pass@k metrics
Multiple sample evaluation
Parallel processing
Quick Start
Run evaluation:

Basic usage:

python src/main.py \
    --model_name <your_model_name> \
    --save_path <output_directory> \
    --num_gpus <number_of_gpus> \
    --batch_size <batch_size> \
    --task <benchmark_name>

Complete example:

python src/main.py \
    --model_name "/path/to/your/model/checkpoint" \
    --task "HumanEval" \
    --save "test/output" \
    --num_gpus 1 \
    --num_samples 1 \
    --k 1 \
    --temperature 0.0 \
    --num_workers 10 \
    --batch_size 200 \
    --max_tokens 4096 \
    --model_type "Chat" \
    --prompt_type "Instruction" \
    --prompt_prefix "" \
    --prompt_suffix "" \
    --trust_remote_code
Key parameters:

model_name: Path to model checkpoint or Hugging Face model ID
task: Benchmark name (HumanEval/MBPP/BigCodeBench/LeetCode)
save: Output directory for results
model_type: Base or Chat
prompt_type: Completion or Instruction
Supported Benchmarks
1. HumanEval
Standard code generation benchmark
Function completion tasks
Python programming problems
Automated test cases
2. MBPP (Mostly Basic Programming Problems)
Basic programming tasks
Few-shot learning support
Python implementation
Test-driven evaluation
3. BigCodeBench
Comprehensive coding tasks
Multiple difficulty levels
Various programming challenges
Extensive test coverage
4. LeetCode
Algorithm problems
Data structure challenges
Multiple difficulty levels
Real-world coding scenarios
Project Structure
OpenCodeEval/
├── src/
│   ├── backend/         # Model backend implementations
│   ├── benchmark/       # Benchmark dataset implementations
│   ├── data/           # Dataset files
│   ├── eval/           # Evaluation utilities
│   └── main.py         # Main entry point
├── LICENSE             # Apache 2.0 license
└── README.md
Configuration
The framework supports various configuration options:

Model configurations:

Model type (Base/Chat)
Number of GPUs
Batch size
Temperature
Max tokens
Prompt configurations:

Prompt type (Completion/Instruction)
Prompt prefix/suffix
Stop words
Evaluation configurations:

Number of samples
Number of workers
Timeout settings
Contributing
Fork the repository
Create your feature branch
Make your changes
Submit a pull request
Please ensure your code follows the project's coding standards and includes appropriate tests.
