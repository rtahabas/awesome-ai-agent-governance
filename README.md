# Awesome AI Agent Governance [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of tools, frameworks, standards, and resources for governing AI agents in production.

AI agents that call tools, write code, and make decisions need the same controls as any other system touching production infrastructure: authentication, authorisation, audit trails, cost controls, and policy enforcement. This list collects the best open-source toolkits, enterprise platforms, standards, and learning resources for teams building or operating governed agentic systems.

**Scope:** Runtime governance of AI agents — policy enforcement, audit trails, access control, cost management, compliance. Not AI safety research, alignment, or general responsible AI ethics.

Contributions welcome. See [CONTRIBUTING.md](CONTRIBUTING.md).

---

## Contents

- [Frameworks and Standards](#frameworks-and-standards)
- [Open-Source Toolkits](#open-source-toolkits)
- [Enterprise Platforms](#enterprise-platforms)
- [Claude Code Governance](#claude-code-governance)
- [Policy Engines](#policy-engines)
- [Audit and Observability](#audit-and-observability)
- [Security and Red-Teaming](#security-and-red-teaming)
- [Agentic Patterns](#agentic-patterns)
- [Learning Resources](#learning-resources)

---

## Frameworks and Standards

Regulatory and standards-body frameworks that govern how AI systems must behave in enterprise and government contexts.

- [NIST AI Risk Management Framework (AI RMF)](https://www.nist.gov/artificial-intelligence/ai-risk-management-framework) — NIST's voluntary framework for managing risk across the AI lifecycle: govern, map, measure, manage.
- [ISO/IEC 42001](https://www.iso.org/standard/81230.html) — International standard for AI management systems. Specifies requirements for establishing, implementing, maintaining, and improving an AI management system within an organisation.
- [EU AI Act](https://artificialintelligenceact.eu/) — EU regulation classifying AI systems by risk level with mandatory requirements for high-risk systems including agentic deployments.
- [NIST Cybersecurity Framework 2.0](https://www.nist.gov/cyberframework) — Applies directly to AI system security, including agent tool access and identity controls.
- [OWASP Agentic AI Top 10](https://owasp.org/www-project-top-10-for-large-language-model-applications/) — The ten most critical security risks for agentic AI systems: prompt injection, insecure tool execution, excessive agency, and more.
- [Anthropic Model Specification](https://www.anthropic.com/research/model-spec) — Anthropic's published specification for how Claude is expected to behave, including corrigibility and deference to operators.
- [MITRE ATLAS](https://atlas.mitre.org/) — Adversarial Threat Landscape for AI Systems. Tactics, techniques, and case studies for attacks against ML systems.

---

## Open-Source Toolkits

Deployable, open-source tools for enforcing governance at runtime.

- [systemprompt-template](https://github.com/systempromptio/systemprompt-template) — Self-hosted governance layer for Claude Code and MCP agents. Audit trail, policy enforcement, cost controls, and role-based access in a single Rust binary. Source-available (BSL-1.1).
- [Microsoft Agent Governance Toolkit](https://github.com/microsoft/agent-governance-toolkit) — Runtime security for AI agents across LangChain, CrewAI, AutoGen, OpenAI Agents, Semantic Kernel, and 15+ frameworks. Covers all 10 OWASP Agentic Top 10 risks. Policy evaluation <0.1ms at 72k ops/sec.
- [Open Policy Agent (OPA)](https://github.com/open-policy-agent/opa) — General-purpose policy engine using Rego. Increasingly used to enforce what tools an AI agent can call and under what conditions.
- [Cedar](https://github.com/cedar-policy/cedar) — AWS's policy language and engine for authorisation decisions. Fine-grained, expressive, and formally verified. Suitable for agent permission models.
- [LiteLLM](https://github.com/BerriAI/litellm) — Proxy layer for LLM API calls with built-in rate limiting, spend tracking, and per-key budget enforcement across all major providers.
- [LangFuse](https://github.com/langfuse/langfuse) — Open-source LLM observability. Traces, evaluations, and cost tracking for LLM applications and agents.
- [Guardrails AI](https://github.com/guardrails-ai/guardrails) — Input and output validation for LLM responses. Define schemas, validators, and correction actions that run at inference time.

---

## Enterprise Platforms

Commercial platforms for teams that need managed AI governance, risk, and compliance.

- [Credo AI](https://www.credo.ai/) — AI governance platform covering risk assessment, compliance mapping (EU AI Act, NIST, ISO 42001), and model monitoring across the AI lifecycle.
- [OneTrust AI Governance](https://www.onetrust.com/solutions/ai-governance/) — Inventory, risk assessment, and compliance controls for AI systems within broader data governance programmes.
- [Lumenova AI](https://www.lumenova.ai/) — Lifecycle governance, risk assessment, and monitoring for enterprise AI deployments.
- [Protect AI](https://protectai.com/) — MLSecOps platform: model scanning, supply chain security, and runtime protection for AI/ML systems.
- [Datadog LLM Observability](https://www.datadoghq.com/product/llm-observability/) — Production monitoring for LLM-powered applications, including latency, cost, and quality tracking.

---

## Claude Code Governance

Tools and resources specifically for governing Claude Code deployments in organisations.

- [systemprompt-template](https://github.com/systempromptio/systemprompt-template) — Governance infrastructure for Claude Code: policy enforcement, audit trail, cost limits, role-based access. Self-hosted Rust binary.
- [awesome-claude-code-security](https://github.com/efij/awesome-claude-code-security) — Curated list of Claude Code hardening resources: MCP security, secrets scanning, injection detection, red-teaming.
- [awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) — The canonical Claude Code community list. Tooling, hooks, slash-commands, and agent skills.
- [Claude Code Documentation](https://docs.anthropic.com/en/docs/claude-code) — Anthropic's official documentation including permissions model, CLAUDE.md configuration, and MCP server setup.
- [Claude Usage Policy](https://www.anthropic.com/legal/usage-policy) — Anthropic's operator and user policies that form the outer governance envelope for any Claude deployment.

---

## Policy Engines

Languages and runtimes for expressing and evaluating access control and governance policy at agent runtime.

- [Open Policy Agent (OPA)](https://www.openpolicyagent.org/) — CNCF-graduated policy engine. Rego policy language. Decouples policy from application code. Widely used for Kubernetes, APIs, and increasingly for agent tool authorisation.
- [Cedar](https://www.cedarpolicy.com/) — AWS-developed policy language designed for authorisation. Formally verified, human-readable, and built for fine-grained permission decisions at high throughput.
- [Casbin](https://github.com/casbin/casbin) — Access control library supporting ACL, RBAC, ABAC models. Language-agnostic with implementations in Go, Rust, Python, Node.js, and more.
- [Rego Playground](https://play.openpolicyagent.org/) — Browser-based environment for writing and testing OPA/Rego policies without local setup.

---

## Audit and Observability

Tools for capturing, storing, and querying what AI agents did and why.

- [LangFuse](https://langfuse.com/) — Open-source. Full trace capture for LLM applications: spans, generations, scores, and costs. Self-hostable.
- [Arize AI](https://arize.com/) — ML and LLM observability platform. Real-time monitoring, drift detection, and prompt debugging for production models.
- [OpenTelemetry](https://opentelemetry.io/) — CNCF standard for distributed tracing, metrics, and logs. The right substrate for building vendor-neutral agent observability pipelines.
- [Helicone](https://github.com/Helicone/helicone) — Open-source LLM observability proxy. Request logging, cost tracking, caching, and rate limiting via a single proxy endpoint.
- [Weights & Biases Weave](https://wandb.ai/site/weave) — Tracing and evaluation for LLM applications and agents. Strong integrations with LangChain, LlamaIndex, and OpenAI.

---

## Security and Red-Teaming

Offensive tooling and threat models for finding weaknesses in agentic systems before attackers do.

- [OWASP Agentic AI Top 10](https://owasp.org/www-project-top-10-for-large-language-model-applications/) — The definitive threat model for agentic systems. Required reading before deploying any agent with tool access.
- [MITRE ATLAS](https://atlas.mitre.org/) — Adversarial ML attack taxonomy with real-world case studies. Covers model evasion, data poisoning, and supply chain attacks.
- [Garak](https://github.com/leondz/garak) — LLM vulnerability scanner. Probes for prompt injection, jailbreaks, data leakage, and hallucination in deployed models.
- [PyRIT](https://github.com/Azure/PyRIT) — Microsoft's Python Risk Identification Toolkit for red-teaming generative AI systems. Covers multi-turn attacks against agents.
- [promptmap](https://github.com/utkusen/promptmap) — Automated prompt injection testing tool for ChatGPT and LLM-integrated applications.

---

## Agentic Patterns

Architecture patterns for building agents that are safe to run in production.

- [awesome-agentic-patterns](https://github.com/nibzard/awesome-agentic-patterns) — Curated collection of production agent patterns including sandboxing, credential management, and human-in-the-loop workflows.
- [Anthropic Agentic AI Guidance](https://www.anthropic.com/research/building-effective-agents) — Anthropic's own guidance on building agents: minimal footprint, explicit confirmation for high-stakes actions, prefer reversible over irreversible.
- [Human-in-the-Loop Patterns](https://lilianweng.github.io/posts/2023-06-23-agent/) — Lilian Weng's comprehensive survey of agent architectures including oversight and intervention patterns.

---

## Learning Resources

Courses, reports, and reference material for practitioners implementing AI governance.

- [NIST AI RMF Playbook](https://airc.nist.gov/Docs/2) — Practical implementation guidance for applying the NIST AI RMF across AI system types.
- [EU AI Act Compliance Checker](https://artificialintelligenceact.eu/assessment/eu-ai-act-compliance-checker/) — Interactive tool for assessing whether an AI system falls under EU AI Act requirements and which obligations apply.
- [State of AI Governance 2025 — Credo AI](https://www.credo.ai/resources) — Annual survey of how enterprises are implementing AI governance programmes.
- [AI Incident Database](https://incidentdatabase.ai/) — Searchable database of AI system failures and harms in deployment. Useful for building threat models and risk assessments.
- [Secure AI Framework (SAIF) — Google](https://safety.google/cybersecurity-advancements/saif/) — Google's framework for securing AI systems across development, deployment, and operation.

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Submissions must be tools or resources that help teams govern AI agents at runtime — not general AI safety research or alignment content.

---

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)

To the extent possible under law, [Ed Burton](https://github.com/Ejb503) has waived all copyright and related rights to this work.
