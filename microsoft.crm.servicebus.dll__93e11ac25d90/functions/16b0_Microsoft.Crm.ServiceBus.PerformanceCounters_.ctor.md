# Microsoft.Crm.ServiceBus.PerformanceCounters::.ctor

- ea: `0x16b0`
- end: `0x16fb`
- name: `Microsoft.Crm.ServiceBus.PerformanceCounters::.ctor`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1700`

## callees

- `0x17d0`

## pseudocode

```c

```

## disassembly

```asm
0x16b0  ldarg.0
0x16b1  call     instance void [mscorlib]System.Object::.ctor()
0x16b6  ldarg.0
0x16b7  ldarg.0
0x16b8  ldstr    aRouterRequestT// "Router Request Timeout"
0x16bd  call     instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::InitializeCounter(string counterName)
0x16c2  stfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::_routerRequestTimeout
0x16c7  ldarg.0
0x16c8  ldarg.0
0x16c9  ldstr    aRouterRequestF// "Router Request Faulted"
0x16ce  call     instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::InitializeCounter(string counterName)
0x16d3  stfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::_routerRequestFaulted
0x16d8  ldarg.0
0x16d9  ldarg.0
0x16da  ldstr    aRouterRequestR// "Router Request Received (Throughput)"
0x16df  call     instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::InitializeCounter(string counterName)
0x16e4  stfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::_routerRequestReceived
0x16e9  ldarg.0
0x16ea  ldarg.0
0x16eb  ldstr    aAppfabricReque// "AppFabric Request Timeout"
0x16f0  call     instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::InitializeCounter(string counterName)
0x16f5  stfld    class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::_appFabricRequestTimeout
0x16fa  ret
```
