# Microsoft.Crm.ReportingServices.ReportingService::DeleteReportHistorySnapshot

- ea: `0x12140`
- end: `0x1215b`
- name: `Microsoft.Crm.ReportingServices.ReportingService::DeleteReportHistorySnapshot`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x12141`: `DeleteReportHistorySnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x12140  ldarg.0
0x12141  ldstr    aDeletereporthi// "DeleteReportHistorySnapshot"
0x12146  ldc.i4.2
0x12147  newarr   [mscorlib]System.Object
0x1214c  dup
0x1214d  ldc.i4.0
0x1214e  ldarg.1
0x1214f  stelem.ref
0x12150  dup
0x12151  ldc.i4.1
0x12152  ldarg.2
0x12153  stelem.ref
0x12154  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x12159  pop
0x1215a  ret
```
