# Microsoft.Crm.Reporting.ReportingServiceProxy::GetPolicies

- ea: `0x33b0`
- end: `0x33fc`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::GetPolicies`
- size: `76`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8ef0`

## pseudocode

```c

```

## disassembly

```asm
0x33b0  newobj   instance void <>c__DisplayClass31_0::.ctor()
0x33b5  stloc.0
0x33b6  ldloc.0
0x33b7  ldarg.0
0x33b8  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass31_0::<>4__this
0x33bd  ldloc.0
0x33be  ldarg.1
0x33bf  stfld    string <>c__DisplayClass31_0::ItemPath
0x33c4  ldloc.0
0x33c5  ldc.i4.0
0x33c6  stfld    bool <>c__DisplayClass31_0::inheritParent
0x33cb  ldloc.0
0x33cc  ldnull
0x33cd  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy[] <>c__DisplayClass31_0::policies
0x33d2  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x33d7  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceGetPoliciesActivityType>::get_Instance()
0x33dc  ldloc.0
0x33dd  ldftn    instance void <>c__DisplayClass31_0::<GetPolicies>b__0()
0x33e3  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x33e8  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x33ed  ldarg.2
0x33ee  ldloc.0
0x33ef  ldfld    bool <>c__DisplayClass31_0::inheritParent
0x33f4  stind.i1
0x33f5  ldloc.0
0x33f6  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy[] <>c__DisplayClass31_0::policies
0x33fb  ret
```
