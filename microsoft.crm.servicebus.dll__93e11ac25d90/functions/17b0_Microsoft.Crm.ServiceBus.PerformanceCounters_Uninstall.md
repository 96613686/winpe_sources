# Microsoft.Crm.ServiceBus.PerformanceCounters::Uninstall

- ea: `0x17b0`
- end: `0x17c7`
- name: `Microsoft.Crm.ServiceBus.PerformanceCounters::Uninstall`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1720`
- `0x3f80`

## callees

- `0x17b0`

## pseudocode

```c

```

## disassembly

```asm
0x17b0  ldsfld   string Microsoft.Crm.ServiceBus.PerformanceCounters::RouterCategoryName
0x17b5  call     bool [System]System.Diagnostics.PerformanceCounterCategory::Exists(string)
0x17ba  brfalse.s loc_17C6
0x17bc  ldsfld   string Microsoft.Crm.ServiceBus.PerformanceCounters::RouterCategoryName
0x17c1  call     void [System]System.Diagnostics.PerformanceCounterCategory::Delete(string)
0x17c6  ret
```
