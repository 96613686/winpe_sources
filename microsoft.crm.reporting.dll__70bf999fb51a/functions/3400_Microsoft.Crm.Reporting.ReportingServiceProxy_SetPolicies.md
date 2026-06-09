# Microsoft.Crm.Reporting.ReportingServiceProxy::SetPolicies

- ea: `0x3400`
- end: `0x3437`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::SetPolicies`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8f40`

## pseudocode

```c

```

## disassembly

```asm
0x3400  newobj   instance void <>c__DisplayClass32_0::.ctor()
0x3405  stloc.0
0x3406  ldloc.0
0x3407  ldarg.0
0x3408  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass32_0::<>4__this
0x340d  ldloc.0
0x340e  ldarg.1
0x340f  stfld    string <>c__DisplayClass32_0::ItemPath
0x3414  ldloc.0
0x3415  ldarg.2
0x3416  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy[] <>c__DisplayClass32_0::Policies
0x341b  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3420  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceSetPoliciesActivityType>::get_Instance()
0x3425  ldloc.0
0x3426  ldftn    instance void <>c__DisplayClass32_0::<SetPolicies>b__0()
0x342c  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x3431  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x3436  ret
```
