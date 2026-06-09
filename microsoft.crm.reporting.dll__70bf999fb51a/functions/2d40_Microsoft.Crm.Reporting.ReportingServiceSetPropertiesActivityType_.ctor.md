# Microsoft.Crm.Reporting.ReportingServiceSetPropertiesActivityType::.ctor

- ea: `0x2d40`
- end: `0x2d4e`
- name: `Microsoft.Crm.Reporting.ReportingServiceSetPropertiesActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2d41`: `ReportingService.SetProperties`

## pseudocode

```c

```

## disassembly

```asm
0x2d40  ldarg.0
0x2d41  ldstr    aReportingservi_14// "ReportingService.SetProperties"
0x2d46  ldc.i4.1
0x2d47  ldc.i4.1
0x2d48  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceSetPropertiesActivityType>::.ctor(string, bool, bool)
0x2d4d  ret
```
