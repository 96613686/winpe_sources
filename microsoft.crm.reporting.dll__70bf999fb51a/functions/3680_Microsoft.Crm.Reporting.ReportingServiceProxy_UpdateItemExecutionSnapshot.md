# Microsoft.Crm.Reporting.ReportingServiceProxy::UpdateItemExecutionSnapshot

- ea: `0x3680`
- end: `0x36b0`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::UpdateItemExecutionSnapshot`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x9240`

## pseudocode

```c

```

## disassembly

```asm
0x3680  newobj   instance void <>c__DisplayClass41_0::.ctor()
0x3685  stloc.0
0x3686  ldloc.0
0x3687  ldarg.0
0x3688  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass41_0::<>4__this
0x368d  ldloc.0
0x368e  ldarg.1
0x368f  stfld    string <>c__DisplayClass41_0::ItemPath
0x3694  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3699  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceUpdateItemExecutionSnapshotActivityType>::get_Instance()
0x369e  ldloc.0
0x369f  ldftn    instance void <>c__DisplayClass41_0::<UpdateItemExecutionSnapshot>b__0()
0x36a5  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x36aa  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x36af  ret
```
