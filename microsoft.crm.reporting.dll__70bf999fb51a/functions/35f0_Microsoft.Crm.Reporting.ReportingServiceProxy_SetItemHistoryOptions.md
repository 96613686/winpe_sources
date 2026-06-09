# Microsoft.Crm.Reporting.ReportingServiceProxy::SetItemHistoryOptions

- ea: `0x35f0`
- end: `0x3636`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::SetItemHistoryOptions`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x9190`

## pseudocode

```c

```

## disassembly

```asm
0x35f0  newobj   instance void <>c__DisplayClass39_0::.ctor()
0x35f5  stloc.0
0x35f6  ldloc.0
0x35f7  ldarg.0
0x35f8  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass39_0::<>4__this
0x35fd  ldloc.0
0x35fe  ldarg.1
0x35ff  stfld    string <>c__DisplayClass39_0::ItemPath
0x3604  ldloc.0
0x3605  ldarg.2
0x3606  stfld    bool <>c__DisplayClass39_0::EnableManualSnapshotCreation
0x360b  ldloc.0
0x360c  ldarg.3
0x360d  stfld    bool <>c__DisplayClass39_0::KeepExecutionSnapshots
0x3612  ldloc.0
0x3613  ldarg.s  4
0x3615  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ScheduleDefinitionOrReference <>c__DisplayClass39_0::Item
0x361a  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x361f  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceSetItemHistoryOptionsActivityType>::get_Instance()
0x3624  ldloc.0
0x3625  ldftn    instance void <>c__DisplayClass39_0::<SetItemHistoryOptions>b__0()
0x362b  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x3630  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x3635  ret
```
