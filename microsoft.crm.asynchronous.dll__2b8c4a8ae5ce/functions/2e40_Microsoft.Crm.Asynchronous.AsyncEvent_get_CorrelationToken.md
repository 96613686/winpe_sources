# Microsoft.Crm.Asynchronous.AsyncEvent::get_CorrelationToken

- ea: `0x2e40`
- end: `0x2e47`
- name: `Microsoft.Crm.Asynchronous.AsyncEvent::get_CorrelationToken`
- size: `7`
- prototype: ``
- caller_count: `11`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x450`
- `0x480`
- `0x3490`
- `0x8e10`
- `0x8e30`
- `0x8e50`
- `0x8e80`
- `0x8ea0`
- `0x9190`
- `0x10720`
- `0x10b50`

## pseudocode

```c

```

## disassembly

```asm
0x2e40  ldarg.0
0x2e41  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken Microsoft.Crm.Asynchronous.AsyncEvent::_correlationToken
0x2e46  ret
```
