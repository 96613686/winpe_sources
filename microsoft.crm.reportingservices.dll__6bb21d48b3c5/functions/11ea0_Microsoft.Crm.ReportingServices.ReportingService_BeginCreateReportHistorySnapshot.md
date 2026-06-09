# Microsoft.Crm.ReportingServices.ReportingService::BeginCreateReportHistorySnapshot

- ea: `0x11ea0`
- end: `0x11eb8`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginCreateReportHistorySnapshot`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11ea1`: `CreateReportHistorySnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x11ea0  ldarg.0
0x11ea1  ldstr    aCreatereporthi// "CreateReportHistorySnapshot"
0x11ea6  ldc.i4.1
0x11ea7  newarr   [mscorlib]System.Object
0x11eac  dup
0x11ead  ldc.i4.0
0x11eae  ldarg.1
0x11eaf  stelem.ref
0x11eb0  ldarg.2
0x11eb1  ldarg.3
0x11eb2  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x11eb7  ret
```
