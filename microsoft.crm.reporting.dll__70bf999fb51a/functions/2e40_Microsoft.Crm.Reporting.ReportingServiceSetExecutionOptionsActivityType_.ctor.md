# Microsoft.Crm.Reporting.ReportingServiceSetExecutionOptionsActivityType::.ctor

- ea: `0x2e40`
- end: `0x2e4e`
- name: `Microsoft.Crm.Reporting.ReportingServiceSetExecutionOptionsActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2e41`: `ReportingService.SetExecutionOptions`

## pseudocode

```c

```

## disassembly

```asm
0x2e40  ldarg.0
0x2e41  ldstr    aReportingservi_22// "ReportingService.SetExecutionOptions"
0x2e46  ldc.i4.1
0x2e47  ldc.i4.1
0x2e48  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceSetExecutionOptionsActivityType>::.ctor(string, bool, bool)
0x2e4d  ret
```
