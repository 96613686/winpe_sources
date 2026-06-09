# Microsoft.Crm.Reporting.ReportingServiceProxy::ListExtensions

- ea: `0x3440`
- end: `0x3470`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::ListExtensions`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x8f90`

## pseudocode

```c

```

## disassembly

```asm
0x3440  newobj   instance void <>c__DisplayClass33_0::.ctor()
0x3445  stloc.0
0x3446  ldloc.0
0x3447  ldarg.0
0x3448  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass33_0::<>4__this
0x344d  ldloc.0
0x344e  ldarg.1
0x344f  stfld    string <>c__DisplayClass33_0::ExtensionType
0x3454  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3459  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceListExtensionsActivityType>::get_Instance()
0x345e  ldloc.0
0x345f  ldftn    instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Extension[] <>c__DisplayClass33_0::<ListExtensions>b__0()
0x3465  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Extension[]>::.ctor(object, native int)
0x346a  call     T0x2B00000A
0x346f  ret
```
