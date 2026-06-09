# Microsoft.Crm.Reporting.ReportingServiceProxy::GetItemType

- ea: `0x3130`
- end: `0x3160`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::GetItemType`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8ba0`

## pseudocode

```c

```

## disassembly

```asm
0x3130  newobj   instance void <>c__DisplayClass21_0::.ctor()
0x3135  stloc.0
0x3136  ldloc.0
0x3137  ldarg.0
0x3138  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass21_0::<>4__this
0x313d  ldloc.0
0x313e  ldarg.1
0x313f  stfld    string <>c__DisplayClass21_0::ItemPath
0x3144  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3149  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceGetItemTypeActivityType>::get_Instance()
0x314e  ldloc.0
0x314f  ldftn    instance string <>c__DisplayClass21_0::<GetItemType>b__0()
0x3155  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x315a  call     T0x2B000004
0x315f  ret
```
