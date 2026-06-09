# Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetReportServerConfigInfo

- ea: `0x8a50`
- end: `0x8a6d`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::BeginGetReportServerConfigInfo`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x8a51`: `GetReportServerConfigInfo`

## pseudocode

```c

```

## disassembly

```asm
0x8a50  ldarg.0
0x8a51  ldstr    aGetreportserve// "GetReportServerConfigInfo"
0x8a56  ldc.i4.1
0x8a57  newarr   [mscorlib]System.Object
0x8a5c  dup
0x8a5d  ldc.i4.0
0x8a5e  ldarg.1
0x8a5f  box      [mscorlib]System.Boolean
0x8a64  stelem.ref
0x8a65  ldarg.2
0x8a66  ldarg.3
0x8a67  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x8a6c  ret
```
