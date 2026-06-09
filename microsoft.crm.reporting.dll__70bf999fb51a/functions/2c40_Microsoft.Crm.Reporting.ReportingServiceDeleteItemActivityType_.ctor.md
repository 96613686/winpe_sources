# Microsoft.Crm.Reporting.ReportingServiceDeleteItemActivityType::.ctor

- ea: `0x2c40`
- end: `0x2c4e`
- name: `Microsoft.Crm.Reporting.ReportingServiceDeleteItemActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2c41`: `ReportingService.DeleteItem`

## pseudocode

```c

```

## disassembly

```asm
0x2c40  ldarg.0
0x2c41  ldstr    aReportingservi_6// "ReportingService.DeleteItem"
0x2c46  ldc.i4.1
0x2c47  ldc.i4.1
0x2c48  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceDeleteItemActivityType>::.ctor(string, bool, bool)
0x2c4d  ret
```
