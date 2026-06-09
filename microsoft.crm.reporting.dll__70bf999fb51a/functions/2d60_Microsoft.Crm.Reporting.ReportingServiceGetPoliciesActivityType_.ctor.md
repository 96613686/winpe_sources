# Microsoft.Crm.Reporting.ReportingServiceGetPoliciesActivityType::.ctor

- ea: `0x2d60`
- end: `0x2d6e`
- name: `Microsoft.Crm.Reporting.ReportingServiceGetPoliciesActivityType::.ctor`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x2d61`: `ReportingService.GetPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x2d60  ldarg.0
0x2d61  ldstr    aReportingservi_15// "ReportingService.GetPolicies"
0x2d66  ldc.i4.1
0x2d67  ldc.i4.1
0x2d68  call     instance void class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceGetPoliciesActivityType>::.ctor(string, bool, bool)
0x2d6d  ret
```
