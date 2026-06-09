# Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCacheRefreshPlan

- ea: `0x9760`
- end: `0x978f`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateCacheRefreshPlan`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x9761`: `CreateCacheRefreshPlan`

## pseudocode

```c

```

## disassembly

```asm
0x9760  ldarg.0
0x9761  ldstr    aCreatecacheref// "CreateCacheRefreshPlan"
0x9766  ldc.i4.5
0x9767  newarr   [mscorlib]System.Object
0x976c  dup
0x976d  ldc.i4.0
0x976e  ldarg.1
0x976f  stelem.ref
0x9770  dup
0x9771  ldc.i4.1
0x9772  ldarg.2
0x9773  stelem.ref
0x9774  dup
0x9775  ldc.i4.2
0x9776  ldarg.3
0x9777  stelem.ref
0x9778  dup
0x9779  ldc.i4.3
0x977a  ldarg.s  4
0x977c  stelem.ref
0x977d  dup
0x977e  ldc.i4.4
0x977f  ldarg.s  5
0x9781  stelem.ref
0x9782  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x9787  ldc.i4.0
0x9788  ldelem.ref
0x9789  castclass [mscorlib]System.String
0x978e  ret
```
