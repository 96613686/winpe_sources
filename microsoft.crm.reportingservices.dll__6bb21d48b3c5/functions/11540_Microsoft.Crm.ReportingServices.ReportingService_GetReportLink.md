# Microsoft.Crm.ReportingServices.ReportingService::GetReportLink

- ea: `0x11540`
- end: `0x1155d`
- name: `Microsoft.Crm.ReportingServices.ReportingService::GetReportLink`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11541`: `GetReportLink`

## pseudocode

```c

```

## disassembly

```asm
0x11540  ldarg.0
0x11541  ldstr    aGetreportlink// "GetReportLink"
0x11546  ldc.i4.1
0x11547  newarr   [mscorlib]System.Object
0x1154c  dup
0x1154d  ldc.i4.0
0x1154e  ldarg.1
0x1154f  stelem.ref
0x11550  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x11555  ldc.i4.0
0x11556  ldelem.ref
0x11557  castclass [mscorlib]System.String
0x1155c  ret
```
