# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheRefreshPlanProperties

- ea: `0x9980`
- end: `0x99d4`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetCacheRefreshPlanProperties`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x9981`: `GetCacheRefreshPlanProperties`

## pseudocode

```c

```

## disassembly

```asm
0x9980  ldarg.0
0x9981  ldstr    aGetcacherefres// "GetCacheRefreshPlanProperties"
0x9986  ldc.i4.1
0x9987  newarr   [mscorlib]System.Object
0x998c  dup
0x998d  ldc.i4.0
0x998e  ldarg.1
0x998f  stelem.ref
0x9990  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x9995  stloc.0
0x9996  ldarg.2
0x9997  ldloc.0
0x9998  ldc.i4.1
0x9999  ldelem.ref
0x999a  castclass [mscorlib]System.String
0x999f  stind.ref
0x99a0  ldarg.3
0x99a1  ldloc.0
0x99a2  ldc.i4.2
0x99a3  ldelem.ref
0x99a4  castclass Microsoft.Crm.ReportingServices2010.CacheRefreshPlanState
0x99a9  stind.ref
0x99aa  ldarg.s  4
0x99ac  ldloc.0
0x99ad  ldc.i4.3
0x99ae  ldelem.ref
0x99af  castclass [mscorlib]System.String
0x99b4  stind.ref
0x99b5  ldarg.s  5
0x99b7  ldloc.0
0x99b8  ldc.i4.4
0x99b9  ldelem.ref
0x99ba  castclass [mscorlib]System.String
0x99bf  stind.ref
0x99c0  ldarg.s  6
0x99c2  ldloc.0
0x99c3  ldc.i4.5
0x99c4  ldelem.ref
0x99c5  castclass class Microsoft.Crm.ReportingServices2010.ParameterValue[]
0x99ca  stind.ref
0x99cb  ldloc.0
0x99cc  ldc.i4.0
0x99cd  ldelem.ref
0x99ce  castclass [mscorlib]System.String
0x99d3  ret
```
