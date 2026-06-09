# Microsoft.Crm.ServiceBus.PerformanceCounters::get_AppFabricRequestTimeout

- ea: `0x1820`
- end: `0x1827`
- name: `Microsoft.Crm.ServiceBus.PerformanceCounters::get_AppFabricRequestTimeout`
- size: `7`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x4940`
- `0x4ab0`
- `0x4c90`
- `0x55a0`

## pseudocode

```c

```

## disassembly

```asm
0x1820  ldarg.0
0x1821  ldfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::_appFabricRequestTimeout
0x1826  ret
```
