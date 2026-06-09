# Microsoft.Crm.Asynchronous.AsyncService::get_PerformanceCounters

- ea: `0xcc0`
- end: `0xcc7`
- name: `Microsoft.Crm.Asynchronous.AsyncService::get_PerformanceCounters`
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
0xcc0  ldarg.0
0xcc1  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncServicePerformanceCounters Microsoft.Crm.Asynchronous.AsyncService::_counters
0xcc6  ret
```
