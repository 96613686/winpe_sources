# Microsoft.Crm.Reporting.ReportingServiceProxy::ListRoles

- ea: `0x34b0`
- end: `0x34e7`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::ListRoles`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x9030`

## pseudocode

```c

```

## disassembly

```asm
0x34b0  newobj   instance void <>c__DisplayClass35_0::.ctor()
0x34b5  stloc.0
0x34b6  ldloc.0
0x34b7  ldarg.0
0x34b8  stfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass35_0::<>4__this
0x34bd  ldloc.0
0x34be  ldarg.1
0x34bf  stfld    string <>c__DisplayClass35_0::SecurityScope
0x34c4  ldloc.0
0x34c5  ldarg.2
0x34c6  stfld    string <>c__DisplayClass35_0::SiteUrl
0x34cb  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x34d0  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Reporting.ReportingServiceListRolesActivityType>::get_Instance()
0x34d5  ldloc.0
0x34d6  ldftn    instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Role[] <>c__DisplayClass35_0::<ListRoles>b__0()
0x34dc  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Role[]>::.ctor(object, native int)
0x34e1  call     T0x2B00000B
0x34e6  ret
```
