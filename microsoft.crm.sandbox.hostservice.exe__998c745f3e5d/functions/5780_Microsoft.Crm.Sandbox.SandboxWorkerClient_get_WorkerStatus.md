# Microsoft.Crm.Sandbox.SandboxWorkerClient::get_WorkerStatus

- ea: `0x5780`
- end: `0x5787`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerClient::get_WorkerStatus`
- size: `7`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x22b0`
- `0x78c0`
- `0xa350`
- `0xcd60`

## pseudocode

```c

```

## disassembly

```asm
0x5780  ldarg.0
0x5781  ldfld    valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxWorkerClient::_workerStatus
0x5786  ret
```
