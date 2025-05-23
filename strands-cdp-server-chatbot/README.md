# Coinbase AgentKit with Strands Agents Framework

This project demonstrates an intelligent agent that interacts with blockchain networks using the Coinbase Developer Platform (CDP) AgentKit, powered by the Strands Agents framework and Amazon Bedrock for AI capabilities.

The agent can perform various blockchain operations like transferring tokens, checking balances, getting crypto prices, and more - all through natural language interactions in a terminal-based interface.

## Features

- **Interactive Chat Mode** - Engage with the agent through natural language to perform blockchain operations
- **Autonomous Mode** - Let the agent autonomously explore blockchain interactions
- **Persistent Wallet Storage** - Maintain the same wallet across sessions
- **AWS Bedrock Integration** - Powered by models on [Amazon Bedrock](https://aws.amazon.com/bedrock/)
- **Strands Agents Framework Integration** - [Strands Agents](https://strandsagents.com/0.1.x/) is a simple-to-use, code-first framework for building agents.

## Requirements

- Python 3.10+
- AWS account with Amazon Bedrock access (and Nova model enabled)
- Coinbase Developer Platform API key
- AWS CLI configured or credentials available

## Environment Variables

Create a `.env` file with the following variables:

```
# Coinbase Developer Platform credentials
CDP_API_KEY_ID=your_cdp_api_key_id
CDP_API_KEY_SECRET=your_cdp_api_key_secret
CDP_WALLET_SECRET=your_wallet_secret

# Optional configurations
NETWORK_ID=base-sepolia  # Defaults to base-sepolia if not specified
ADDRESS=your_wallet_address  # Optional, will create a new wallet if not provided
IDEMPOTENCY_KEY=your_idempotency_key  # Optional, only used when creating a new wallet

# AWS credentials for Bedrock
AWS_ACCESS_KEY_ID=your_aws_access_key
AWS_SECRET_ACCESS_KEY=your_aws_secret_key
AWS_REGION=us-east-1
```

## Installation

1. Clone the repository
   ```
   git clone https://github.com/yourusername/cdp-agentkit-strands.git
   cd cdp-agentkit-strands
   ```

2. Create a virtual environment
   ```
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies
   ```
   pip install -r requirements.txt
   ```

## Running the Chatbot

```
python chatbot.py
```

You'll be prompted to choose between two modes:

1. **Chat Mode** - Interactive conversation with the agent
2. **Autonomous Mode** - Agent performs actions on its own at regular intervals

## Example Prompts

Try asking the agent to:

- "What's my wallet address and balance?"
- "What is the current price of ETH?"
- "Request some test tokens from the faucet"
- "Transfer 0.01 ETH to a random address"
- "Deploy an ERC-20 token with a supply of 1 million"

## AWS Bedrock Setup

To use this agent, you need:

1. An AWS account with [Amazon Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/model-access.html) access.
2. [Enable Bedrock Model access for selected models on Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/model-access-modify.html). This solution uses Amazon Nova Premier, but you can change to any model suported on [Amazon Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/models-supported.html).
3. Set-up Amazon Bedrock model [inference profiles](https://docs.aws.amazon.com/bedrock/latest/userguide/inference-profiles.html).
4. [Proper IAM permissions](https://docs.aws.amazon.com/bedrock/latest/userguide/security-iam.html) to invoke Amazon Bedrock models.
5. AWS credentials configured in your environment.


## Troubleshooting

- **5XX errors**: If you encounter server errors, wait a moment and try again
- **Authentication failures**: Verify your CDP and AWS credentials
- **Model access issues**: Ensure you have proper access to the Bedrock models in your AWS account
