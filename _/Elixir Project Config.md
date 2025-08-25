# Elixir Project Configuration

*Only applies when working on Elixir projects*

## Tidewave MCP Server

- **Server**: Tidewave Elixir MCP server may be available
- **Availability**: Only runs when project is running
- **Handling**: If unavailable, notify user but continue without errors

## MCP Usage Guidelines (Elixir projects only)

- Always check if MCP tools are available before using
- If Tidewave MCP is not running:
  - Inform user: "Tidewave MCP server is not running"
  - Continue with standard file operations
  - Don't error out or stop workflow
- If Tidewave MCP is available:
  - Use it for enhanced Elixir/Ash operations
  - Prefer MCP tools over standard file operations where applicable

## Fallback Behavior (Elixir projects)

- File operations: Use standard Read/Write tools if MCP unavailable
- Code analysis: Use Grep/Glob if MCP tools unavailable
- Documentation: Use standard tools if MCP doc tools unavailable

## Ash Framework Best Practices

- Use `mix ash.codegen` instead of `mix ecto.migrate` 
- Use `mix ash.migrate` instead of `mix ecto.migrate`
- Never run `mix ecto.create` and `mix ecto.migrate` directly in Ash projects
- Resources are defined in code, migrations generated via `mix ash.codegen`
- Always run `mix ash.codegen` after resource changes
