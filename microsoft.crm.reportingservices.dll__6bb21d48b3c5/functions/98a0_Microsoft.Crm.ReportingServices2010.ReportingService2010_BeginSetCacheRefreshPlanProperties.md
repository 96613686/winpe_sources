# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginSetCacheRefreshPlanProperties

- ea: `0x98a0`
- end: `0x98cc`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginSetCacheRefreshPlanProperties`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x98a1`: `SetCacheRefreshPlanProperties`

## pseudocode

```c

```

## disassembly

```asm
0x98a0  ldarg.0
0x98a1  ldstr    aSetcacherefres// "SetCacheRefreshPlanProperties"
0x98a6  ldc.i4.5
0x98a7  newarr   [mscorlib]System.Object
0x98ac  dup
0x98ad  ldc.i4.0
0x98ae  ldarg.1
0x98af  stelem.ref
0x98b0  dup
0x98b1  ldc.i4.1
0x98b2  ldarg.2
0x98b3  stelem.ref
0x98b4  dup
0x98b5  ldc.i4.2
0x98b6  ldarg.3
0x98b7  stelem.ref
0x98b8  dup
0x98b9  ldc.i4.3
0x98ba  ldarg.s  4
0x98bc  stelem.ref
0x98bd  dup
0x98be  ldc.i4.4
0x98bf  ldarg.s  5
0x98c1  stelem.ref
0x98c2  ldarg.s  6
0x98c4  ldarg.s  7
0x98c6  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x98cb  ret
```
