<h1 align="center">ksef2 MCP</h1>

<h3 align="center">
  Work-in-progress MCP server for KSeF automation on top of the ksef2 SDK.
</h3>

<p align="center">
  The project experiments with MCP tools for agent-assisted KSeF workflows:
  building valid FA(3) invoices, working with invoice downloads, and exposing
  selected SDK capabilities through structured tools.
</p>

<div align="center">
  <br>
  <a href="https://ksef2.stacking.me/mcp/intro/" title="ksef2 MCP documentation">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/stacking-hq/ksef2-mcp/main/docs/assets/ksef2-mcp-light-logo.png">
      <img src="https://raw.githubusercontent.com/stacking-hq/ksef2-mcp/main/docs/assets/ksef2-mcp-dark-logo.png" alt="ksef2 MCP" width="460">
    </picture>
  </a>
  <br>
  <br>
  <p>
    <a href="https://github.com/pre-commit/pre-commit"><img src="https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit" alt="pre-commit enabled"></a>
    <a href="https://github.com/astral-sh/ruff"><img src="https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/ruff/main/assets/badge/v2.json" alt="Ruff"></a>
    <a href="https://opensource.org/licenses/MIT"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="MIT license"></a>
    <a href="https://www.python.org/downloads/"><img src="https://img.shields.io/badge/python-3.12+-blue.svg" alt="Python 3.12+"></a>
  </p>
</div>

## What is ksef2 MCP?

`ksef2-mcp` is an MCP server built on top of the
[`ksef2`](https://github.com/stacking-hq/ksef2) Python SDK. Its premise is to
make KSeF workflows available to MCP clients and AI agents through typed tools
instead of free-form XML or ad hoc shell commands.

The current focus is experimentation around invoice-builder toolchains,
download/export workflows, and evaluation harnesses for agent behavior. The MCP
tool surface is still evolving, so use the SDK documentation as the stable
reference for KSeF behavior.

This project is not published, endorsed, or supported by Poland's Ministry of
Finance. Official KSeF documentation remains the source of truth for API
behavior.

## Install

Prepare a local checkout with all dependency groups:

```bash
uv sync --all-groups
```

Requires Python 3.12 or newer.

## Run

Start the server from the repository:

```bash
uv run --env-file .env ksef2-mcp
```

or:

```bash
uv run --env-file .env python -m ksef2_mcp
```

The transport shape and production packaging are still being refined.

## Project Premise

The MCP server is intended to become an agent-facing companion to the SDK and
CLI:

- SDK: typed Python interface for application code
- CLI: terminal and CI automation
- MCP: structured tools for agent-assisted KSeF workflows

The MCP project should stay thin where possible and delegate KSeF API behavior
to the SDK.

## Documentation

- Online docs: <https://ksef2.stacking.me/mcp/intro/>
- SDK docs: <https://ksef2.stacking.me/sdk/intro/>
- SDK repository: [`stacking-hq/ksef2`](https://github.com/stacking-hq/ksef2)

## Development

```bash
just sync
just check
```

The source docs are intentionally light while the MCP tool surface is still
changing. Keep stable KSeF workflow documentation in the SDK docs.

## License

[MIT](LICENSE)
