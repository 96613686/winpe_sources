# Microsoft.Crm.Reporting.ReportingServiceGetItemDefinitionActivityType::.ctor

- ea: `0x2c80`
- end: `0x2c8e`
- name: `Microsoft.Crm.Reporting.ReportingServiceGetItemDefinitionActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2c81`: `ReportingService.GetItemDefinition`

## pseudocode

```c

```

## disassembly

```asm
0x2c80  ldarg.0
0x2c81  ldstr    aReportingservi_8// "ReportingService.GetItemDefinition"
0x2c86  ldc.i4.1
0x2c87  ldc.i4.1
0x2c88  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceGetItemDefinitionActivityType>::.ctor(string, bool, bool)
0x2c8d  ret
```
