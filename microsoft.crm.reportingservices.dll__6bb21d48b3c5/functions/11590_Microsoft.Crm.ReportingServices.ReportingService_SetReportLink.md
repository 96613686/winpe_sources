# Microsoft.Crm.ReportingServices.ReportingService::SetReportLink

- ea: `0x11590`
- end: `0x115ab`
- name: `Microsoft.Crm.ReportingServices.ReportingService::SetReportLink`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11591`: `SetReportLink`

## pseudocode

```c

```

## disassembly

```asm
0x11590  ldarg.0
0x11591  ldstr    aSetreportlink// "SetReportLink"
0x11596  ldc.i4.2
0x11597  newarr   [mscorlib]System.Object
0x1159c  dup
0x1159d  ldc.i4.0
0x1159e  ldarg.1
0x1159f  stelem.ref
0x115a0  dup
0x115a1  ldc.i4.1
0x115a2  ldarg.2
0x115a3  stelem.ref
0x115a4  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x115a9  pop
0x115aa  ret
```
