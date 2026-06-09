# Microsoft.Crm.Reporting.ReportingServiceProxy::SetItemParameters

- ea: `0x3260`
- end: `0x3297`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::SetItemParameters`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8d50`

## pseudocode

```c

```

## disassembly

```asm
0x3260  newobj   instance void <>c__DisplayClass26_0::.ctor()
0x3265  stloc.0
0x3266  ldloc.0
0x3267  ldarg.0
0x3268  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass26_0::<>4__this
0x326d  ldloc.0
0x326e  ldarg.1
0x326f  stfld    string <>c__DisplayClass26_0::ItemPath
0x3274  ldloc.0
0x3275  ldarg.2
0x3276  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[] <>c__DisplayClass26_0::Parameters
0x327b  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3280  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceSetItemParametersActivityType>::get_Instance()
0x3285  ldloc.0
0x3286  ldftn    instance void <>c__DisplayClass26_0::<SetItemParameters>b__0()
0x328c  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x3291  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x3296  ret
```
