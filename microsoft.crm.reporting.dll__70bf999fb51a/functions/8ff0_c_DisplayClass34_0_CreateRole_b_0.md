# <>c__DisplayClass34_0::<CreateRole>b__0

- ea: `0x8ff0`
- end: `0x901e`
- name: `<>c__DisplayClass34_0::<CreateRole>b__0`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x2f60`
- `0x36c0`

## pseudocode

```c

```

## disassembly

```asm
0x8ff0  ldarg.0
0x8ff1  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass34_0::<>4__this
0x8ff6  call     instance void Microsoft.Crm.Reporting.ReportingServiceProxy::SetTelemetryCustomProperties()
0x8ffb  ldarg.0
0x8ffc  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass34_0::<>4__this
0x9001  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x9006  ldarg.0
0x9007  ldfld    string <>c__DisplayClass34_0::Name
0x900c  ldarg.0
0x900d  ldfld    string <>c__DisplayClass34_0::Description
0x9012  ldarg.0
0x9013  ldfld    string[] <>c__DisplayClass34_0::TaskIDs
0x9018  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateRole(string, string, string[])
0x901d  ret
```
