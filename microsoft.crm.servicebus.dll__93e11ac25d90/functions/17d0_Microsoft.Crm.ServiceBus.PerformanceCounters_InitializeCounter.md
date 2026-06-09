# Microsoft.Crm.ServiceBus.PerformanceCounters::InitializeCounter

- ea: `0x17d0`
- end: `0x17e5`
- name: `Microsoft.Crm.ServiceBus.PerformanceCounters::InitializeCounter`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x16b0`

## pseudocode

```c

```

## disassembly

```asm
0x17d0  ldsfld   string Microsoft.Crm.ServiceBus.PerformanceCounters::RouterCategoryName
0x17d5  ldarg.1
0x17d6  ldc.i4.0
0x17d7  newobj   instance void [System]System.Diagnostics.PerformanceCounter::.ctor(string, string, bool)
0x17dc  dup
0x17dd  ldc.i4.0
0x17de  conv.i8
0x17df  callvirt instance void [System]System.Diagnostics.PerformanceCounter::set_RawValue(int64)
0x17e4  ret
```
