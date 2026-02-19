# Aerospace AI Audit Framework

A research framework for AI decision auditability in safety-critical aerospace systems, focused on meeting FAA and EASA airworthiness certification requirements.

## Problem

ML models are entering aircraft design, manufacturing, and maintenance decision workflows. Current airworthiness certification standards — DO-178C (software), DO-254 (hardware), ARP4754A (systems) — were built for deterministic, fully traceable systems. They have no mechanism to audit, log, or explain non-deterministic AI-driven decisions.

This creates a certification gap: AI systems that influence safety-critical outcomes cannot be certified under existing frameworks because their decision processes are not auditable to the standard required by FAA and EASA.

## Approach

This project explores a **digital twin architecture for AI decision logging** — a structured approach to capturing, storing, and replaying the decision context of ML models operating in aerospace workflows.

The core idea: treat the AI decision process itself as an artifact that can be versioned, traced, and audited — the same way configuration-managed software is handled under DO-178C.

### Architecture Concepts

- **Decision Record Layer** — Structured logging of model inputs, outputs, confidence scores, feature attributions, and environmental context at inference time
- **Traceability Graph** — Mapping AI decisions back to requirements, training data provenance, and validation evidence (aligned with ARP4754A traceability expectations)
- **Replay and Audit Interface** — Ability to reconstruct and inspect the decision state at any historical point, supporting post-incident analysis and certification evidence packages
- **Compliance Mapping** — Explicit mapping between framework outputs and certification objectives (DO-178C Table A-1 through A-10, EASA AI Roadmap 2.0 concepts)

## Current Status

**Active doctoral research** at George Washington University (AI/ML). This repository will evolve as the research progresses.

Current phase: architecture definition and literature review. No production code yet — the initial focus is on formalizing the decision logging schema and mapping it to certification evidence requirements.

## Tech Stack (Exploratory)

- **Python** — primary implementation language
- **MLflow** — experiment tracking and model registry integration
- **Apache Kafka / event streaming** — decision event capture pipeline
- **Graph databases (Neo4j)** — traceability graph storage
- **JSON Schema / OpenTelemetry** — decision record format standardization
- **Docker** — containerized audit replay environments

## Relevant Standards and Frameworks

| Standard | Scope | Relevance |
|---|---|---|
| DO-178C | Airborne software | Software assurance levels, verification objectives |
| DO-254 | Airborne hardware | Hardware assurance methodology (analogies for AI hardware) |
| ARP4754A | Aircraft systems | System-level safety assessment and traceability |
| EASA AI Roadmap 2.0 | AI in aviation | Emerging regulatory concepts for ML certification |
| NIST AI RMF | AI risk management | Risk-based framework applicable to aerospace AI |
| SAE AIR6988 | AI in aeronautical systems | Industry guidance on AI development assurance |

## Related Work

- [OpenAI Evals](https://github.com/openai/evals) — Framework for systematic LLM evaluation (see [my fork](https://github.com/reidmcgill/evals))
- EASA Artificial Intelligence Roadmap 2.0
- FAA Roadmap for AI Safety Assurance

## Author

**Reid McGill**
Doctoral Researcher, George Washington University  | 
Founder, [Fionn Labs](https://fionnlabs.com)  | 
Boeing BCA — Digital Engineering 


## License

MIT
