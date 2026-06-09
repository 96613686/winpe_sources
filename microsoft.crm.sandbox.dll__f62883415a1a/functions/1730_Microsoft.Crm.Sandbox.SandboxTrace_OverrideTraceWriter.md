# Microsoft.Crm.Sandbox.SandboxTrace::OverrideTraceWriter

- ea: `0x1730`
- end: `0x173a`
- name: `Microsoft.Crm.Sandbox.SandboxTrace::OverrideTraceWriter`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1730`

## pseudocode

```c

```

## disassembly

```asm
0x1730  ldarg.0
0x1731  brfalse.s loc_1739
0x1733  ldarg.0
0x1734  stsfld   class Microsoft.Crm.Sandbox.ISandboxTraceWriter Microsoft.Crm.Sandbox.SandboxTrace::_traceWriter
0x1739  ret
```
