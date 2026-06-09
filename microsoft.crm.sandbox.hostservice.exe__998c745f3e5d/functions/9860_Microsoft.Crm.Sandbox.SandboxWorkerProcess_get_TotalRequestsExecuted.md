# Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_TotalRequestsExecuted

- ea: `0x9860`
- end: `0x986e`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_TotalRequestsExecuted`
- size: `14`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4240`
- `0xba70`
- `0xbf70`
- `0xcd60`

## pseudocode

```c

```

## disassembly

```asm
0x9860  ldarg.0
0x9861  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_totalWorkerExecuteCount
0x9866  ldarg.0
0x9867  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_totalWorkerPingCount
0x986c  add
0x986d  ret
```
