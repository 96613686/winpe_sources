# Microsoft.Crm.Reporting.ReportingServiceProxy::CreateCatalogItem

- ea: `0x34f0`
- end: `0x3563`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::CreateCatalogItem`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x9080`

## pseudocode

```c

```

## disassembly

```asm
0x34f0  newobj   instance void <>c__DisplayClass36_0::.ctor()
0x34f5  stloc.0
0x34f6  ldloc.0
0x34f7  ldarg.0
0x34f8  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass36_0::<>4__this
0x34fd  ldloc.0
0x34fe  ldarg.1
0x34ff  stfld    string <>c__DisplayClass36_0::ItemType
0x3504  ldloc.0
0x3505  ldarg.2
0x3506  stfld    string <>c__DisplayClass36_0::Name
0x350b  ldloc.0
0x350c  ldarg.3
0x350d  stfld    string <>c__DisplayClass36_0::Parent
0x3512  ldloc.0
0x3513  ldarg.s  4
0x3515  stfld    bool <>c__DisplayClass36_0::Overwrite
0x351a  ldloc.0
0x351b  ldarg.s  5
0x351d  stfld    unsigned int8[] <>c__DisplayClass36_0::Definition
0x3522  ldloc.0
0x3523  ldarg.s  6
0x3525  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] <>c__DisplayClass36_0::Properties
0x352a  ldloc.0
0x352b  ldnull
0x352c  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Warning[] <>c__DisplayClass36_0::warningsList
0x3531  ldloc.0
0x3532  ldnull
0x3533  stfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem <>c__DisplayClass36_0::catalogItem
0x3538  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x353d  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceCreateCatalogItemActivityType>::get_Instance()
0x3542  ldloc.0
0x3543  ldftn    instance void <>c__DisplayClass36_0::<CreateCatalogItem>b__0()
0x3549  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x354e  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryExtensions::Execute(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryActivityType, class [mscorlib]System.Action)
0x3553  ldarg.s  7
0x3555  ldloc.0
0x3556  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Warning[] <>c__DisplayClass36_0::warningsList
0x355b  stind.ref
0x355c  ldloc.0
0x355d  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem <>c__DisplayClass36_0::catalogItem
0x3562  ret
```
