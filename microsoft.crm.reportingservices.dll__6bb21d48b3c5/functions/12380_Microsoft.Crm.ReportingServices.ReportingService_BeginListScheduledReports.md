# Microsoft.Crm.ReportingServices.ReportingService::BeginListScheduledReports

- ea: `0x12380`
- end: `0x12398`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginListScheduledReports`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12381`: `ListScheduledReports`

## pseudocode

```c

```

## disassembly

```asm
0x12380  ldarg.0
0x12381  ldstr    aListscheduledr// "ListScheduledReports"
0x12386  ldc.i4.1
0x12387  newarr   [mscorlib]System.Object
0x1238c  dup
0x1238d  ldc.i4.0
0x1238e  ldarg.1
0x1238f  stelem.ref
0x12390  ldarg.2
0x12391  ldarg.3
0x12392  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x12397  ret
```
