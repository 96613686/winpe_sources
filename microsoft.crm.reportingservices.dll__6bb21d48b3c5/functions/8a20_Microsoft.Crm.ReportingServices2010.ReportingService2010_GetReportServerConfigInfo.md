# Microsoft.Crm.ReportingServices2010.ReportingService2010::GetReportServerConfigInfo

- ea: `0x8a20`
- end: `0x8a42`
- name: `Microsoft.Crm.ReportingServices2010.ReportingService2010::GetReportServerConfigInfo`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x8a21`: `GetReportServerConfigInfo`

## pseudocode

```c

```

## disassembly

```asm
0x8a20  ldarg.0
0x8a21  ldstr    aGetreportserve// "GetReportServerConfigInfo"
0x8a26  ldc.i4.1
0x8a27  newarr   [mscorlib]System.Object
0x8a2c  dup
0x8a2d  ldc.i4.0
0x8a2e  ldarg.1
0x8a2f  box      [mscorlib]System.Boolean
0x8a34  stelem.ref
0x8a35  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x8a3a  ldc.i4.0
0x8a3b  ldelem.ref
0x8a3c  castclass [mscorlib]System.String
0x8a41  ret
```
