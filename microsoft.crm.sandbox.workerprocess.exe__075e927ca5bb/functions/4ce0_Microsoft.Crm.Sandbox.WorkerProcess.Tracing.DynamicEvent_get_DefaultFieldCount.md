# Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::get_DefaultFieldCount

- ea: `0x4ce0`
- end: `0x4ce8`
- name: `Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::get_DefaultFieldCount`
- size: `8`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4d90`
- `0x4fb0`
- `0x5000`

## pseudocode

```c

```

## disassembly

```asm
0x4ce0  ldsfld   string[] Microsoft.Crm.Sandbox.WorkerProcess.Tracing.DynamicEvent::DefaultFieldNames
0x4ce5  ldlen
0x4ce6  conv.i4
0x4ce7  ret
```
