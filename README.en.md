# MSGA

**An Agent Skill for reviewing whether sales-facing documents are actionable.**

[简体中文](README.md) · [Skill instructions](SKILL.md) · [Examples](EXAMPLES.md) · [MIT License](LICENSE)

MSGA reviews sales training documents, SOPs, action guides, business plans, and policy explanations. It can also run before a newly written document is delivered. It does not assume a particular industry, product, sales model, or organizational structure.

## Four review dimensions

| Dimension | Questions |
| --- | --- |
| Definitions and action standards | Are key terms clear? Who does what, to what standard, with what evidence of completion? |
| Workflow and paths | Can the reader reach the intended outcome? Are branches, handoffs, exceptions, and exit conditions clear? |
| Prerequisites and dependencies | Are required customer conditions, resources, permissions, people, and prior work explicit? |
| Help and support | Who can help, through which channel, with what information, and what happens if support is unavailable? |

MSGA produces a scoped conclusion, a four-dimension overview, prioritized findings, source evidence, concrete replacement text, unresolved questions, and acceptance criteria.

Unknown owners, thresholds, channels, and service commitments remain explicitly unconfirmed. Missing documentation is not proof that a resource does not exist. A short notice is reviewed against its own purpose rather than being expanded into an entire sales playbook.

## Try without installation

Provide [SKILL.md](SKILL.md) in an AI conversation, ask the assistant to follow it, and supply the document to review. Supported file formats depend on the host tool.

```text
Use the MSGA instructions to review this sales-facing document. Give me a complete diagnosis, prioritized findings, and concrete revisions. Respond in English.
```

## Install in Codex

On macOS / Linux with Git installed, back up any existing `msga` skill directory before installing:

```bash
git clone https://github.com/zm0218/MSGA.git "${CODEX_HOME:-$HOME/.codex}/skills/msga"
```

Start a new task and invoke:

```text
Use $msga to review this sales SOP. Include evidence, priorities, proposed replacement text, and facts that still need confirmation. Respond in English.
```

Alternatively, download the repository ZIP and place the folder containing `SKILL.md` and `agents/` in the skill directory under the name `msga`.

The core instructions are Markdown with no required API, Python, or Node runtime. Other skill-capable hosts can use the instructions according to their own loading and invocation rules. `agents/openai.yaml` contains Codex-specific UI metadata.

## Invocation and scope

Implicit selection is enabled, but selection depends on the host. MSGA reviews documents provided or identified in the current task; it does not watch folders or scan colleagues' files. A review request does not authorize overwriting source files. Requested edits remain within the user's authorized scope.

The canonical instructions and default output language are Chinese. You can request another output language. This English README is a usage guide, not a separate rule set.

## Examples and validation

[EXAMPLES.md](EXAMPLES.md) contains three fictional scenarios: an incomplete trial process, a complete short notice, and a document with unavailable attachments.

The initial version passed skill-format validation and Codex discovery checks, with three scenario walkthroughs performed by the authoring assistant. There is no independent model benchmark, real sales-user study, or measured effectiveness claim. A document review is not organizational approval or proof of business outcomes.

## Contribute

Open an Issue or Pull Request with the document's purpose, expected behavior, observed behavior, and a minimal anonymized example you have permission to share. Do not include customer information, internal pricing, credentials, or confidential policies.

Proposed rules should address a concrete execution problem and include both a positive detection example and a case that should not be flagged.

## License

[MIT](LICENSE).
