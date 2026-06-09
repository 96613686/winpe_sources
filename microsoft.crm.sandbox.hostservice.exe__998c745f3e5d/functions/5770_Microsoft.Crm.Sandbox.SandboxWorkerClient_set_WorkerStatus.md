# Microsoft.Crm.Sandbox.SandboxWorkerClient::set_WorkerStatus

- ea: `0x5770`
- end: `0x5778`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerClient::set_WorkerStatus`
- size: `8`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x22b0`
- `0x78c0`
- `0x9de0`
- `0xa350`
- `0xae00`
- `0xb090`
- `0xb250`

## pseudocode

```c

```

## disassembly

```asm
0x5770  ldarg.0
0x5771  ldarg.1
0x5772  stfld    valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxWorkerClient::_workerStatus
0x5777  ret
```
