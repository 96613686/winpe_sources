# Microsoft.Crm.Asynchronous.AsyncService::get_AsyncStartStopActivityId

- ea: `0xc50`
- end: `0xc57`
- name: `Microsoft.Crm.Asynchronous.AsyncService::get_AsyncStartStopActivityId`
- size: `7`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xe20`
- `0x12c0`
- `0xa620`

## pseudocode

```c

```

## disassembly

```asm
0xc50  ldarg.0
0xc51  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncService::_asyncStartStopActivityId
0xc56  ret
```
