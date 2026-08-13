# Pipeline Doctor

An agent that fixes a failing test suite and loops until it is green:

1. **Plan** - run the tests and read the failure.
2. **Act** - read the code, find the bug, write a fix.
3. **Observe** - re-run the suite and read the result.
4. **Verify** - a truthful verifier re-checks the suite; if anything still
   fails, the feedback is fed back and the loop repeats.

Zero third-party dependencies - pure Python standard library.

## Run it

```cmd
python run.py
```

This uses a deterministic offline demo brain - no API key, reproducible run.
The agent works on a fresh copy of the sample repo each time.

For a real model, create a `.env` file (git-ignored) and run:

```text
DEEPSEEK_API_KEY=sk-your-key-here
```

```cmd
python run.py deepseek
```

## Outputs

- `trace.json` - the full step-by-step trace (thought, tool call,
  observation, self-check, retry).
- The interactive step-through of a real DeepSeek run:
  [visuals/pipeline-doctor.html](visuals/pipeline-doctor.html)

Part of the [Agentic Workflow Lab](https://github.com/ryanreo/agentic-workflow-lab).
