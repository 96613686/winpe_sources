# Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::IsLoggingAllowedForEvent

- ea: `0x118d0`
- end: `0x118fe`
- name: `Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::IsLoggingAllowedForEvent`
- size: `46`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x5eb0`
- `0x10b50`
- `0x10ea0`

## callees

- `0x118d0`
- `0x11900`
- `0x11940`
- `0x11960`

## pseudocode

```c

```

## disassembly

```asm
0x118d0  call     class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryManager::get_Instance()
0x118d5  callvirt instance bool [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryManager::IsVerboseEnabled()
0x118da  brtrue.s loc_118FC
0x118dc  ldarg.1
0x118dd  brfalse.s loc_118FA
0x118df  ldarg.0
0x118e0  ldarg.1
0x118e1  call     instance bool Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::IsSystemJob(class Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0x118e6  brtrue.s loc_118FA
0x118e8  ldarg.0
0x118e9  ldarg.1
0x118ea  call     instance bool Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::IsScalegroupOrganizationMaintenanceJob(class Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0x118ef  brtrue.s loc_118FA
0x118f1  ldarg.0
0x118f2  ldarg.1
0x118f3  call     instance bool Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLoggingEvaluator::IsJobTypeCanbeIgnored(class Microsoft.Crm.Asynchronous.IAsyncEvent asyncEvent)
0x118f8  brfalse.s loc_118FC
0x118fa  ldc.i4.0
0x118fb  ret
0x118fc  ldc.i4.1
0x118fd  ret
```
