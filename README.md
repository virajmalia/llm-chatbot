# The Llama4U Project
[![Python application](https://github.com/virajmalia/llama4u/actions/workflows/CI.yml/badge.svg)](https://github.com/virajmalia/llama4u/actions/workflows/CI.yml)

Llama4U is a privacy-focused AI assistant developed using [Ollama][1], [LangChain][2] and [Llama3][3]. A completely free AI solution that can be hosted locally, while providing online capabilities in a responsible and user-controllable way.

#### *APIs that have usage limitations or require keys to be registered with an online account won't be added to this project.*

## Steps to run
1. Host `llama3` model from [Ollama][1] on your computer.
2. Clone this repository.

There are 2 usage modes:

### LangServe
3. `pip install -U langchain-cli && langchain serve`
4. The default server is hosted on `127.0.0.1` or `localhost` and port `8000`.
5. Playground can be accessed at `<host_ip>:<port>/llama4u/playground`.

### CLI
3. `cd app/ && pip install -e .`
4. `llama4u`
5. `llama4u --help` for full CLI.

## List of chat commands

- `/search`: Perform online search using DuckDuckGo

## Current motivations for feature-set
- Perplexity AI
- ChatGPT/GPT4o

## System requirements
- Powerful CPU or Nvidia GPU (>=8G VRAM)
- Ubuntu 22.04
- Works on WSL2 with nvidia CUDA

Use these steps to setup nvidia cuda drivers, if GPU is not being used:
```bash
# nvidia GPU setup for Ubuntu 22.04
curl -fSsL https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/3bf863cc.pub | sudo gpg --dearmor | sudo tee /usr/share/keyrings/nvidia-drivers.gpg > /dev/null 2>&1
echo 'deb [signed-by=/usr/share/keyrings/nvidia-drivers.gpg] https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/ /' | sudo tee /etc/apt/sources.list.d/nvidia-drivers.list
sudo apt update
sudo apt install cuda-toolkit-12-4
export PATH=/usr/local/cuda-12/bin:~/.local/bin:${PATH}
export CUDACXX=$(which nvcc)
if -z $CUDACXX; then
    echo "nvcc not found in PATH."
    exit /b 1
fi
echo $CUDACXX && $CUDACXX --version
```

## Credits
- Meta, for the open source Llama models
- Ollama
- LangChain community

[1]: https://github.com/ollama/ollama
[2]: https://python.langchain.com/v0.1/docs/get_started/introduction/
[3]: https://huggingface.co/blog/llama3
