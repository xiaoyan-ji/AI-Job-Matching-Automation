# AI Job Matching Automation

An AI-powered workflow that turns recurring job searches into personalized, ranked recommendations using n8n, OpenAI, and automated email delivery.

## Problem & Solution

Manual job searching involves repeatedly collecting listings, checking requirements, comparing opportunities, and deciding where to apply.

This project combines these steps into one workflow. It compares job descriptions with a candidate profile, applies a consistent scoring framework, and delivers bilingual recommendations for human review.

## Results

- Completed **100+ successful workflow executions** during personal use.
- Used daily to support real job-search and application decisions.
- Delivers recommendations each morning at **7:00 AM** in the live setup.
- Consolidates job discovery, screening, scoring, ranking, and email reporting into one automated process.

Execution counts reflect personal operating experience. Time savings and recommendation accuracy have not been formally measured.

## Workflow

1. **Retrieve listings:** Collect job postings through an HTTP API.
2. **Prepare data:** Normalize job fields, remove duplicates, and filter unsuitable roles.
3. **Assess fit:** Use GPT-4.1-mini to compare job descriptions with the candidate profile.
4. **Validate outputs:** Parse structured JSON and apply business rules to scores and recommendations.
5. **Prioritize opportunities:** Rank eligible jobs and select a shortlist.
6. **Deliver recommendations:** Send an English–Chinese email with match explanations, concerns, and application guidance.

The workflow supports application decisions; it does not automatically submit applications.

## Scoring Framework

Business requirements are translated into a six-dimension, 100-point framework:

| Dimension | Maximum points |
|---|---:|
| Target role fit | 25 |
| Business scenario fit | 20 |
| Technical and analytical skill fit | 20 |
| Experience evidence | 15 |
| Seniority feasibility | 15 |
| Location and work arrangement | 5 |
| **Total** | **100** |

Screening rules address technical requirements, seniority, location, and role suitability. Recommendations are intended for human review rather than treated as objective hiring probabilities.

## Validation & Iteration

- Defined prompts and a structured JSON schema for consistent downstream processing.
- Added deterministic rules to constrain recommendations and maintain score consistency.
- Refined screening criteria after reviewing unsuitable recommendations.
- Combined AI-generated explanations with rule-based filtering and ranking.

## Skills Demonstrated

**AI solution design · Business requirements analysis · Prompt engineering · LLM integration · API integration · Workflow automation · Output validation · Process optimization · Decision support**

## Technology

- **n8n:** Workflow orchestration
- **OpenAI GPT-4.1-mini:** Job matching and explanations
- **HTTP API / Apify:** Job data retrieval
- **JavaScript:** Normalization, filtering, validation, and ranking
- **Gmail:** Recommendation delivery

## Public Template

`AI_Job_Matching_PUBLIC.json` is a sanitized portfolio template. Credentials, recipient details, and personal file paths have been removed or replaced. Scheduled execution is disabled in this public version.

To adapt it:

1. Import the JSON into a compatible n8n instance.
2. Configure your Apify token and OpenAI/Gmail credentials.
3. Set the recipient email and an accessible candidate-profile file path.
4. Review the search criteria, prompts, and scoring rules.
5. Run a manual test and inspect the recommendations.
6. Confirm the workflow timezone, enable the schedule, and publish or activate the workflow.

The public template requires configuration before use.
