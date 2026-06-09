# Microsoft.Crm.ServiceBus.PerformanceCounters::Install

- ea: `0x1720`
- end: `0x17aa`
- name: `Microsoft.Crm.ServiceBus.PerformanceCounters::Install`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3e50`

## callees

- `0x17b0`

## pseudocode

```c

```

## disassembly

```asm
0x1720  call     void Microsoft.Crm.ServiceBus.PerformanceCounters::Uninstall()
0x1725  newobj   instance void [System]System.Diagnostics.CounterCreationDataCollection::.ctor()
0x172a  stloc.0
0x172b  ldloc.0
0x172c  ldstr    aRouterRequestT// "Router Request Timeout"
0x1731  ldstr    aTheNumberOfTim// "The number of timeouts seen making requ"...
0x1736  ldc.i4   0x10100
0x173b  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1740  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1745  pop
0x1746  ldloc.0
0x1747  ldstr    aRouterRequestF// "Router Request Faulted"
0x174c  ldstr    aTheNumberOfReq// "The number of requests made on the faul"...
0x1751  ldc.i4   0x10100
0x1756  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x175b  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1760  pop
0x1761  ldloc.0
0x1762  ldstr    aRouterRequestR// "Router Request Received (Throughput)"
0x1767  ldstr    aTheNumberOfReq_0// "The number of requests received by the "...
0x176c  ldc.i4   0x10100
0x1771  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1776  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x177b  pop
0x177c  ldloc.0
0x177d  ldstr    aAppfabricReque// "AppFabric Request Timeout"
0x1782  ldstr    aTheNumberOfTim_0// "The number of timeouts seen making requ"...
0x1787  ldc.i4   0x10100
0x178c  newobj   instance void [System]System.Diagnostics.CounterCreationData::.ctor(string, string, valuetype [System]System.Diagnostics.PerformanceCounterType)
0x1791  callvirt instance int32 [System]System.Diagnostics.CounterCreationDataCollection::Add(class [System]System.Diagnostics.CounterCreationData)
0x1796  pop
0x1797  ldsfld   string Microsoft.Crm.ServiceBus.PerformanceCounters::RouterCategoryName
0x179c  ldstr    aMicrosoftCrmRo// "Microsoft CRM Router performance counte"...
0x17a1  ldc.i4.0
0x17a2  ldloc.0
0x17a3  call     class [System]System.Diagnostics.PerformanceCounterCategory [System]System.Diagnostics.PerformanceCounterCategory::Create(string, string, valuetype [System]System.Diagnostics.PerformanceCounterCategoryType, class [System]System.Diagnostics.CounterCreationDataCollection)
0x17a8  pop
0x17a9  ret
```
