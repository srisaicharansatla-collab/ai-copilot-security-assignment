# Securing an AI Root Cause Analysis and Ticket Resolution Copilot

Cybersecurity assignment: threat model, secure architecture, AI-specific defences, safe automation,
application security and red team plan for an AI copilot that reads logs, finds root causes,
suggests fixes and closes simple tickets.

## Contents

| Path | What it is |
|---|---|
| `report/AI_Copilot_Security_Report.docx` | Full report, Parts A to H, with references (IEEE) |
| `report/AI_Copilot_Security_Report.pdf` | PDF copy of the report |
| `presentation/AI_Copilot_Security_Presentation.pptx` | 10-slide presentation with speaker notes |
| `diagrams/dfd.png`, `diagrams/architecture.png` | Data flow diagram and final architecture |
| `diagrams/*.dot` | Graphviz sources (`dot -Tpng -Gdpi=150 dfd.dot -o dfd.png`) |
| `policy/auto_remediation_policy.yaml` | Example policy-engine rules (ticket tiers, caps, kill switch) |
| `policy/masking_rules.yaml` | Example masking rule set for the ingestion gateway |

## Summary of the design

- The model is an untrusted adviser: it proposes, deterministic code decides, signed runbooks act.
- Read-only analyzer and write-capable executor use separate identities, networks and approvals.
- Logs and tickets are masked before they reach the model (fail-closed), and verified with canary secrets.
- Tickets are sorted into automatic, approve-first and human-only tiers by a policy engine.
- A red team exercise in staging covers seven attack scenarios mapped to MITRE ATT&CK and ATLAS.

## Notes

- Replace the placeholders (name, roll number, date) on the cover page and slides.
- Baselines and targets in Part F are planning figures; replace them with measured values.
- Check that the latest editions of OWASP, NIST and the Indian DPDP rules are cited before submitting.
- The YAML files are illustrative and not production-ready.
