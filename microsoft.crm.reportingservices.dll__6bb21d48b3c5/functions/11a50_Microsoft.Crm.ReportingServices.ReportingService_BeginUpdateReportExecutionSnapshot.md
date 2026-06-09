# Microsoft.Crm.ReportingServices.ReportingService::BeginUpdateReportExecutionSnapshot

- ea: `0x11a50`
- end: `0x11a68`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginUpdateReportExecutionSnapshot`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x11a51`: `UpdateReportExecutionSnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x11a50  ldarg.0
0x11a51  ldstr    aUpdatereportex// "UpdateReportExecutionSnapshot"
0x11a56  ldc.i4.1
0x11a57  newarr   [mscorlib]System.Object
0x11a5c  dup
0x11a5d  ldc.i4.0
0x11a5e  ldarg.1
0x11a5f  stelem.ref
0x11a60  ldarg.2
0x11a61  ldarg.3
0x11a62  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x11a67  ret
```
