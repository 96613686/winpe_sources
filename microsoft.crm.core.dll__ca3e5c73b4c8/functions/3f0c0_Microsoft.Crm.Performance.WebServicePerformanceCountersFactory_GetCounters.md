# Microsoft.Crm.Performance.WebServicePerformanceCountersFactory::GetCounters

- ea: `0x3f0c0`
- end: `0x3f0f3`
- name: `Microsoft.Crm.Performance.WebServicePerformanceCountersFactory::GetCounters`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x3f0c0`
- `0x3f100`

## string_xrefs

- `0x3f0c1`: `CrmService`
- `0x3f0ce`: `MetadataService`

## pseudocode

```c

```

## disassembly

```asm
0x3f0c0  ldarg.1
0x3f0c1  ldstr    aCrmservice// "CrmService"
0x3f0c6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3f0cb  brtrue.s loc_3F0DC
0x3f0cd  ldarg.1
0x3f0ce  ldstr    aMetadataservic// "MetadataService"
0x3f0d3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3f0d8  brtrue.s loc_3F0E0
0x3f0da  br.s     loc_3F0E4
0x3f0dc  ldc.i4.0
0x3f0dd  stloc.0
0x3f0de  br.s     loc_3F0EB
0x3f0e0  ldc.i4.1
0x3f0e1  stloc.0
0x3f0e2  br.s     loc_3F0EB
0x3f0e4  ldarg.0
0x3f0e5  ldfld    class NullWebServicePerformanceCounters Microsoft.Crm.Performance.WebServicePerformanceCountersFactory::_nullCounter
0x3f0ea  ret
0x3f0eb  ldarg.0
0x3f0ec  ldloc.0
0x3f0ed  call     instance class Microsoft.Crm.Performance.IWebServicePerformanceCounters Microsoft.Crm.Performance.WebServicePerformanceCountersFactory::GetCounters(valuetype Microsoft.Crm.Performance.WebServiceType type)
0x3f0f2  ret
```
