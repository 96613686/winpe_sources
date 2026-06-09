# Microsoft.Crm.Sandbox.SandboxTracingService::get_TraceInfo

- ea: `0x1e80`
- end: `0x1e8c`
- name: `Microsoft.Crm.Sandbox.SandboxTracingService::get_TraceInfo`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x7b0`
- `0x10d0`
- `0x1240`

## pseudocode

```c

```

## disassembly

```asm
0x1e80  ldarg.0
0x1e81  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Sandbox.SandboxTracingService::_stringBuilder
0x1e86  callvirt instance string [mscorlib]System.Object::ToString()
0x1e8b  ret
```
