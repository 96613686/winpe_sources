# Microsoft.Crm.ReportingServices.ReportingService::BeginGetReportLink

- ea: `0x11560`
- end: `0x11578`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginGetReportLink`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11561`: `GetReportLink`

## pseudocode

```c

```

## disassembly

```asm
0x11560  ldarg.0
0x11561  ldstr    aGetreportlink// "GetReportLink"
0x11566  ldc.i4.1
0x11567  newarr   [mscorlib]System.Object
0x1156c  dup
0x1156d  ldc.i4.0
0x1156e  ldarg.1
0x1156f  stelem.ref
0x11570  ldarg.2
0x11571  ldarg.3
0x11572  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x11577  ret
```
