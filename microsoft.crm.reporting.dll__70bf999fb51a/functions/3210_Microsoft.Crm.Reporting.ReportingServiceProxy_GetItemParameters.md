# Microsoft.Crm.Reporting.ReportingServiceProxy::GetItemParameters

- ea: `0x3210`
- end: `0x325e`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::GetItemParameters`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x8cf0`

## pseudocode

```c

```

## disassembly

```asm
0x3210  newobj   instance void <>c__DisplayClass25_0::.ctor()
0x3215  stloc.0
0x3216  ldloc.0
0x3217  ldarg.0
0x3218  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass25_0::<>4__this
0x321d  ldloc.0
0x321e  ldarg.1
0x321f  stfld    string <>c__DisplayClass25_0::ItemPath
0x3224  ldloc.0
0x3225  ldarg.2
0x3226  stfld    string <>c__DisplayClass25_0::HistoryID
0x322b  ldloc.0
0x322c  ldarg.3
0x322d  stfld    bool <>c__DisplayClass25_0::ForRendering
0x3232  ldloc.0
0x3233  ldarg.s  4
0x3235  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue[] <>c__DisplayClass25_0::Values
0x323a  ldloc.0
0x323b  ldarg.s  5
0x323d  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials[] <>c__DisplayClass25_0::Credentials
0x3242  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3247  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceGetItemParametersActivityType>::get_Instance()
0x324c  ldloc.0
0x324d  ldftn    instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[] <>c__DisplayClass25_0::<GetItemParameters>b__0()
0x3253  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[]>::.ctor(object, native int)
0x3258  call     T0x2B000007
0x325d  ret
```
