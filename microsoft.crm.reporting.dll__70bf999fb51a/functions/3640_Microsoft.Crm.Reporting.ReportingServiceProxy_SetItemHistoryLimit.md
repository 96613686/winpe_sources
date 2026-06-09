# Microsoft.Crm.Reporting.ReportingServiceProxy::SetItemHistoryLimit

- ea: `0x3640`
- end: `0x367e`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::SetItemHistoryLimit`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x91f0`

## pseudocode

```c

```

## disassembly

```asm
0x3640  newobj   instance void <>c__DisplayClass40_0::.ctor()
0x3645  stloc.0
0x3646  ldloc.0
0x3647  ldarg.0
0x3648  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass40_0::<>4__this
0x364d  ldloc.0
0x364e  ldarg.1
0x364f  stfld    string <>c__DisplayClass40_0::ItemPath
0x3654  ldloc.0
0x3655  ldarg.2
0x3656  stfld    bool <>c__DisplayClass40_0::UseSystem
0x365b  ldloc.0
0x365c  ldarg.3
0x365d  stfld    int32 <>c__DisplayClass40_0::HistoryLimit
0x3662  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3667  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceSetItemHistoryLimitActivityType>::get_Instance()
0x366c  ldloc.0
0x366d  ldftn    instance void <>c__DisplayClass40_0::<SetItemHistoryLimit>b__0()
0x3673  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x3678  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x367d  ret
```
