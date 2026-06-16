# AI Support Triage Agent (n8n)

## Overview

This project is a lean AI-powered support triage workflow built using n8n. The workflow demonstrates how webhooks, APIs, JSON data structures, AI agents, and automation can be combined to process customer support requests automatically.

The workflow receives a customer message through a webhook, analyzes it using an AI model, determines the issue and priority level, and routes the ticket accordingly.

---

## Objective

The goal of this project is to demonstrate:

* Webhook-based automation
* JSON data handling between nodes
* AI-powered ticket analysis
* API integration using AI models
* Conditional routing using IF nodes
* Automated email notifications
* Real-time workflow execution

---

## Workflow Architecture

Webhook
↓
Edit Fields
↓
AI Agent
↓
Code (Parse Response)
↓
IF (Priority Check)
↙              ↘
High Priority   Normal Priority
↓                   ↓
Send Email      Update Status
↓                   ↓
Respond to Webhook

---

## Nodes Used

### 1. Webhook

Receives customer requests in JSON format.

### 2. Edit Fields

Extracts and formats customer data.

### 3. AI Agent

Analyzes the customer message and identifies:

* Issue
* Priority
* Summary

### 4. Code Node

Parses AI-generated JSON output.

### 5. IF Node

Routes tickets based on priority level.

### 6. Send Email

Sends alerts for high-priority support tickets.

### 7. Respond to Webhook

Returns the final response to the requester.

---

## Sample Input

```json
{
  "customer_name": "Rahul Sharma",
  "message": "My payment failed and I need urgent help."
}
```

## Sample AI Output

```json
{
  "customer_name": "Rahul Sharma",
  "issue": "Payment Failure",
  "priority": "High",
  "summary": "Customer payment failed and requires urgent assistance."
}
```

## Sample Response

```json
{
  "status": "success",
  "customer": "Rahul Sharma",
  "priority": "High",
  "issue": "Payment Failure"
}
```

---

## Author
Roshani Gabhale


