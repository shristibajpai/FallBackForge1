
---
name: api-recovery
description: Analyze API failures and recommend safe retry, fallback, and recovery strategies.
---

# API Recovery Skill

## Purpose
Help developers diagnose API failures and design safe recovery strategies.

## Workflow
1. Classify the failure: timeout, HTTP 429 rate limit, HTTP 5xx server error, or invalid response.
2. Identify likely causes without inventing facts.
3. Recommend a retry policy appropriate to the failure.
4. Recommend a fallback strategy.
5. Identify risks and safeguards.
6. Provide a recovery checklist and illustrative Python code.

## Retry Guidelines
- Use exponential backoff with jitter where appropriate.
- Respect Retry-After when provided by a rate-limited service.
- Set a maximum retry count.
- Do not retry non-idempotent requests without safeguards.
- Avoid retrying permanent client errors without correcting the request.

## Fallback Strategies
- cached_response: return a valid, suitably fresh cached result.
- secondary_provider: use a configured alternative provider.
- graceful_degradation: return reduced functionality.
- fail_safely: return a clear error without fabricating data.

## Safety Rules
- Never claim a real API was tested or repaired unless it actually was.
- Distinguish simulated results from real network behavior.
- Do not expose API keys, tokens, or credentials.
- Do not recommend infinite retries.
- Explain important trade-offs and failure risks.

## Required Output
Return:
1. Failure diagnosis
2. Recommended recovery strategy
3. Retry policy
4. Fallback plan
5. Risks and safeguards
6. Recovery checklist
7. Suggested Python implementation

Keep recommendations concise, actionable, and appropriate for the selected failure type.
