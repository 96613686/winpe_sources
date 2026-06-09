# Microsoft.Crm.Reporting.ReportingServiceProxy::MoveItem

- ea: `0x3570`
- end: `0x35a7`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::MoveItem`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x90f0`

## pseudocode

```c

```

## disassembly

```asm
0x3570  newobj   instance void <>c__DisplayClass37_0::.ctor()
0x3575  stloc.0
0x3576  ldloc.0
0x3577  ldarg.0
0x3578  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass37_0::<>4__this
0x357d  ldloc.0
0x357e  ldarg.1
0x357f  stfld    string <>c__DisplayClass37_0::ItemPath
0x3584  ldloc.0
0x3585  ldarg.2
0x3586  stfld    string <>c__DisplayClass37_0::Target
0x358b  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3590  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceMoveItemActivityType>::get_Instance()
0x3595  ldloc.0
0x3596  ldftn    instance void <>c__DisplayClass37_0::<MoveItem>b__0()
0x359c  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x35a1  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x35a6  ret
```
