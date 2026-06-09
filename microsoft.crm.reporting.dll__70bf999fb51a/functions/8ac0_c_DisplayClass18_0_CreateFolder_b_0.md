# <>c__DisplayClass18_0::<CreateFolder>b__0

- ea: `0x8ac0`
- end: `0x8aee`
- name: `<>c__DisplayClass18_0::<CreateFolder>b__0`
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
0x8ac0  ldarg.0
0x8ac1  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass18_0::<>4__this
0x8ac6  call     instance void Microsoft.Crm.Reporting.ReportingServiceProxy::SetTelemetryCustomProperties()
0x8acb  ldarg.0
0x8acc  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass18_0::<>4__this
0x8ad1  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x8ad6  ldarg.0
0x8ad7  ldfld    string <>c__DisplayClass18_0::Folder
0x8adc  ldarg.0
0x8add  ldfld    string <>c__DisplayClass18_0::Parent
0x8ae2  ldarg.0
0x8ae3  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] <>c__DisplayClass18_0::Properties
0x8ae8  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.CatalogItem [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010::CreateFolder(string, string, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[])
0x8aed  ret
```
