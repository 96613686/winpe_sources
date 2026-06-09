# Microsoft.Crm.ReportingServices.ReportingService::BeginDeleteReportHistorySnapshot

- ea: `0x12160`
- end: `0x1217d`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginDeleteReportHistorySnapshot`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12161`: `DeleteReportHistorySnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x12160  ldarg.0
0x12161  ldstr    aDeletereporthi// "DeleteReportHistorySnapshot"
0x12166  ldc.i4.2
0x12167  newarr   [mscorlib]System.Object
0x1216c  dup
0x1216d  ldc.i4.0
0x1216e  ldarg.1
0x1216f  stelem.ref
0x12170  dup
0x12171  ldc.i4.1
0x12172  ldarg.2
0x12173  stelem.ref
0x12174  ldarg.3
0x12175  ldarg.s  4
0x12177  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x1217c  ret
```
