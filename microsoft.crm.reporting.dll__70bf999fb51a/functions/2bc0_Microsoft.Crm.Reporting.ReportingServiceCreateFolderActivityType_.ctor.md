# Microsoft.Crm.Reporting.ReportingServiceCreateFolderActivityType::.ctor

- ea: `0x2bc0`
- end: `0x2bce`
- name: `Microsoft.Crm.Reporting.ReportingServiceCreateFolderActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2bc1`: `ReportingService.CreateFolder`

## pseudocode

```c

```

## disassembly

```asm
0x2bc0  ldarg.0
0x2bc1  ldstr    aReportingservi_2// "ReportingService.CreateFolder"
0x2bc6  ldc.i4.1
0x2bc7  ldc.i4.1
0x2bc8  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceCreateFolderActivityType>::.ctor(string, bool, bool)
0x2bcd  ret
```
