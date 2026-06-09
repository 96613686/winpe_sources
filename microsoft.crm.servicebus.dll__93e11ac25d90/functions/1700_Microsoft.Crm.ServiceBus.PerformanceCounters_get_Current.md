# Microsoft.Crm.ServiceBus.PerformanceCounters::get_Current

- ea: `0x1700`
- end: `0x1717`
- name: `Microsoft.Crm.ServiceBus.PerformanceCounters::get_Current`
- size: `23`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180`
- `0x3ff0`
- `0x4940`
- `0x4ab0`
- `0x4c90`
- `0x55a0`

## callees

- `0x16b0`
- `0x1700`

## pseudocode

```c

```

## disassembly

```asm
0x1700  ldsfld   class Microsoft.Crm.ServiceBus.PerformanceCounters Microsoft.Crm.ServiceBus.PerformanceCounters::_current
0x1705  brtrue.s loc_1711
0x1707  newobj   instance void Microsoft.Crm.ServiceBus.PerformanceCounters::.ctor()
0x170c  stsfld   class Microsoft.Crm.ServiceBus.PerformanceCounters Microsoft.Crm.ServiceBus.PerformanceCounters::_current
0x1711  ldsfld   class Microsoft.Crm.ServiceBus.PerformanceCounters Microsoft.Crm.ServiceBus.PerformanceCounters::_current
0x1716  ret
```
