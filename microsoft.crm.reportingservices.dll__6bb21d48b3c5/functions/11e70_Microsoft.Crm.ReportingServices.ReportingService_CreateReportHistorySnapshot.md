# Microsoft.Crm.ReportingServices.ReportingService::CreateReportHistorySnapshot

- ea: `0x11e70`
- end: `0x11e99`
- name: `Microsoft.Crm.ReportingServices.ReportingService::CreateReportHistorySnapshot`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x11e71`: `CreateReportHistorySnapshot`

## pseudocode

```c

```

## disassembly

```asm
0x11e70  ldarg.0
0x11e71  ldstr    aCreatereporthi// "CreateReportHistorySnapshot"
0x11e76  ldc.i4.1
0x11e77  newarr   [mscorlib]System.Object
0x11e7c  dup
0x11e7d  ldc.i4.0
0x11e7e  ldarg.1
0x11e7f  stelem.ref
0x11e80  call     instance object[] [System.Web.Services]System.Web.Services.Protocols.SoapHttpClientProtocol::Invoke(string, object[])
0x11e85  stloc.0
0x11e86  ldarg.2
0x11e87  ldloc.0
0x11e88  ldc.i4.1
0x11e89  ldelem.ref
0x11e8a  castclass class Microsoft.Crm.ReportingServices.Warning[]
0x11e8f  stind.ref
0x11e90  ldloc.0
0x11e91  ldc.i4.0
0x11e92  ldelem.ref
0x11e93  castclass [mscorlib]System.String
0x11e98  ret
```
