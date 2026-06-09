# Microsoft.Crm.Asynchronous.AsyncService::get_DebugContext

- ea: `0xc60`
- end: `0xc67`
- name: `Microsoft.Crm.Asynchronous.AsyncService::get_DebugContext`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180`
- `0x2010`

## pseudocode

```c

```

## disassembly

```asm
0xc60  ldarg.0
0xc61  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncDebugContext Microsoft.Crm.Asynchronous.AsyncService::_debugContext
0xc66  ret
```
