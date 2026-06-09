# Microsoft.Crm.Asynchronous.AsyncService::get_Context

- ea: `0xc40`
- end: `0xc47`
- name: `Microsoft.Crm.Asynchronous.AsyncService::get_Context`
- size: `7`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xe0`
- `0x860`
- `0xe20`
- `0x1120`
- `0x12c0`
- `0x13d0`
- `0x1650`
- `0x16a0`
- `0x1fc0`
- `0x51d0`

## pseudocode

```c

```

## disassembly

```asm
0xc40  ldarg.0
0xc41  ldfld    valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceContext Microsoft.Crm.Asynchronous.AsyncService::_context
0xc46  ret
```
