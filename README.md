# Pentest AI Script

This script automates basic web security scanning using **Nikto**, **WhatWeb**, and **Gobuster** against OWASP Juice Shop, and sends the results to a **local AI model via Ollama** for analysis.

The final output is written to a Markdown (`.md`) report with tool outputs and a summarized AI-generated analysis.

---

## 🛠 Requirements

- **WSL2** with Kali Linux
- **Ollama** running locally on the Windows host
- **OWASP Juice Shop** running in Docker
- Common pentest tools: `nikto`, `whatweb`, `gobuster`

---

## ⚙️ Configuration

Make sure to adjust the following in the script if needed:

- **Target URL** (default: `http://localhost:3000`)
- **Ollama IP address** (`OLLAMA_IP`) — usually resolved with:
  ```bash
  ip route | grep default | awk '{print $3}'

	•	Port for Ollama (OLLAMA_PORT) — default is 11434

🚀 Usage

bash pentest_ai.sh http://localhost:3000

The script will:
	1.	Scan the target with Nikto, WhatWeb, and Gobuster
	2.	Save raw outputs
	3.	Send data to your local LLM for analysis
	4.	Append the response to the Markdown report

⸻

📄 Example Output

The report includes:
	•	Tool headers
	•	Raw output in code blocks
	•	AI-generated analysis and recommendations

⸻

🧠 Model Notes

The prompt is engineered for LLaMA 3, but works with most local LLMs that support :instruct or instruction-based formats.

Prompt examples and discussion are available in the main report.


