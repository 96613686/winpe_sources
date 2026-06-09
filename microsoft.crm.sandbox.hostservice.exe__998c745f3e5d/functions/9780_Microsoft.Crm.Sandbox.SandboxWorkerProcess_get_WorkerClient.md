# Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerClient

- ea: `0x9780`
- end: `0x9787`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerClient`
- size: `7`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x22b0`
- `0x78c0`
- `0xb1d0`
- `0xc860`
- `0xcd60`

## pseudocode

```c

```

## disassembly

```asm
0x9780  ldarg.0
0x9781  ldfld    class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerProcess::_workerClient
0x9786  ret
```
