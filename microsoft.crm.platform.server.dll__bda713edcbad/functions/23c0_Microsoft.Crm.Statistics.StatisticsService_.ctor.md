# Microsoft.Crm.Statistics.StatisticsService::.ctor

- ea: `0x23c0`
- end: `0x23e3`
- name: `Microsoft.Crm.Statistics.StatisticsService::.ctor`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1cc0`
- `0x2140`

## callees

- `0x56a80`

## string_xrefs

- `0x23c1`: `StatisticsService`
- `0x23d2`: `StatisticsService created`

## pseudocode

```c

```

## disassembly

```asm
0x23c0  ldarg.0
0x23c1  ldstr    aStatisticsserv_1// "StatisticsService"
0x23c6  call     instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::.ctor(string platformName)
0x23cb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x23d0  ldc.i4.s 0x14
0x23d2  ldstr    aStatisticsserv_2// "StatisticsService created"
0x23d7  ldc.i4.0
0x23d8  newarr   [mscorlib]System.Object
0x23dd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x23e2  ret
```
