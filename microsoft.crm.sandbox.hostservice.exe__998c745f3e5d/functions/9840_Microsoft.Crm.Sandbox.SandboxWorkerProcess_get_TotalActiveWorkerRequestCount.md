# Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_TotalActiveWorkerRequestCount

- ea: `0x9840`
- end: `0x984e`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_TotalActiveWorkerRequestCount`
- size: `14`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1190`
- `0x2040`
- `0x4240`
- `0x7230`
- `0xba70`
- `0xbf70`
- `0xcd60`

## pseudocode

```c

```

## disassembly

```asm
0x9840  ldarg.0
0x9841  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_activeWorkerExecuteCount
0x9846  ldarg.0
0x9847  ldfld    int32 Microsoft.Crm.Sandbox.SandboxWorkerProcess::_activeWorkerPingCount
0x984c  add
0x984d  ret
```
