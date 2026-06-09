# Microsoft.Crm.Reporting.ReportingServiceSetDataSourceContentsActivityType::.ctor

- ea: `0x2ba0`
- end: `0x2bae`
- name: `Microsoft.Crm.Reporting.ReportingServiceSetDataSourceContentsActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2ba1`: `ReportingService.SetDataSourceContents`

## pseudocode

```c

```

## disassembly

```asm
0x2ba0  ldarg.0
0x2ba1  ldstr    aReportingservi_1// "ReportingService.SetDataSourceContents"
0x2ba6  ldc.i4.1
0x2ba7  ldc.i4.1
0x2ba8  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceSetDataSourceContentsActivityType>::.ctor(string, bool, bool)
0x2bad  ret
```
