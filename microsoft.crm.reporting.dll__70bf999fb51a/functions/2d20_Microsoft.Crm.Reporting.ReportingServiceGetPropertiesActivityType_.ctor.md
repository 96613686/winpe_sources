# Microsoft.Crm.Reporting.ReportingServiceGetPropertiesActivityType::.ctor

- ea: `0x2d20`
- end: `0x2d2e`
- name: `Microsoft.Crm.Reporting.ReportingServiceGetPropertiesActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2d21`: `ReportingService.GetProperties`

## pseudocode

```c

```

## disassembly

```asm
0x2d20  ldarg.0
0x2d21  ldstr    aReportingservi_13// "ReportingService.GetProperties"
0x2d26  ldc.i4.1
0x2d27  ldc.i4.1
0x2d28  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceGetPropertiesActivityType>::.ctor(string, bool, bool)
0x2d2d  ret
```
