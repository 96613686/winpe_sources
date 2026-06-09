# Microsoft.Crm.ReportingServices.ReportingService::ListScheduledReports

- ea: `0x12360`
- end: `0x1237d`
- name: `Microsoft.Crm.ReportingServices.ReportingService::ListScheduledReports`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12361`: `ListScheduledReports`

## pseudocode

```c

```

## disassembly

```asm
0x12360  ldarg.0
0x12361  ldstr    aListscheduledr// "ListScheduledReports"
0x12366  ldc.i4.1
0x12367  newarr   [mscorlib]System.Object
0x1236c  dup
0x1236d  ldc.i4.0
0x1236e  ldarg.1
0x1236f  stelem.ref
0x12370  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x12375  ldc.i4.0
0x12376  ldelem.ref
0x12377  castclass class Microsoft.Crm.ReportingServices.CatalogItem[]
0x1237c  ret
```
