# Microsoft.Crm.Reporting.ReportingServiceProxy::GetItemDefinition

- ea: `0x31e0`
- end: `0x3210`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::GetItemDefinition`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8ca0`

## pseudocode

```c

```

## disassembly

```asm
0x31e0  newobj   instance void <>c__DisplayClass24_0::.ctor()
0x31e5  stloc.0
0x31e6  ldloc.0
0x31e7  ldarg.0
0x31e8  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass24_0::<>4__this
0x31ed  ldloc.0
0x31ee  ldarg.1
0x31ef  stfld    string <>c__DisplayClass24_0::ItemPath
0x31f4  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x31f9  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceGetItemDefinitionActivityType>::get_Instance()
0x31fe  ldloc.0
0x31ff  ldftn    instance unsigned int8[] <>c__DisplayClass24_0::<GetItemDefinition>b__0()
0x3205  newobj   instance void class [mscorlib]System.Func`1<unsigned int8[]>::.ctor(object, native int)
0x320a  call     T0x2B000006
0x320f  ret
```
