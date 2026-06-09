# Microsoft.Crm.ReportingServices.ReportingService::BeginSetReportLink

- ea: `0x115b0`
- end: `0x115cd`
- name: `Microsoft.Crm.ReportingServices.ReportingService::BeginSetReportLink`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x115b1`: `SetReportLink`

## pseudocode

```c

```

## disassembly

```asm
0x115b0  ldarg.0
0x115b1  ldstr    aSetreportlink// "SetReportLink"
0x115b6  ldc.i4.2
0x115b7  newarr   [mscorlib]System.Object
0x115bc  dup
0x115bd  ldc.i4.0
0x115be  ldarg.1
0x115bf  stelem.ref
0x115c0  dup
0x115c1  ldc.i4.1
0x115c2  ldarg.2
0x115c3  stelem.ref
0x115c4  ldarg.3
0x115c5  ldarg.s  4
0x115c7  call     instance class [mscorlib]System.IAsyncResult [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::BeginInvoke(string, object[], class [mscorlib]System.AsyncCallback, object)
0x115cc  ret
```
