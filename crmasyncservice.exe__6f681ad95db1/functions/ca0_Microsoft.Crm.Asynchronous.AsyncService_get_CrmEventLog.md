# Microsoft.Crm.Asynchronous.AsyncService::get_CrmEventLog

- ea: `0xca0`
- end: `0xca7`
- name: `Microsoft.Crm.Asynchronous.AsyncService::get_CrmEventLog`
- size: `7`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xe0`
- `0x180`

## pseudocode

```c

```

## disassembly

```asm
0xca0  ldarg.0
0xca1  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog Microsoft.Crm.Asynchronous.AsyncService::_eventLog
0xca6  ret
```
