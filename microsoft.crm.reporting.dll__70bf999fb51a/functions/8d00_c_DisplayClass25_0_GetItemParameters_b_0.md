# <>c__DisplayClass25_0::<GetItemParameters>b__0

- ea: `0x8d00`
- end: `0x8d3a`
- name: `<>c__DisplayClass25_0::<GetItemParameters>b__0`
- size: `58`
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
0x8d00  ldarg.0
0x8d01  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass25_0::<>4__this
0x8d06  call     instance void Microsoft.Crm.Reporting.ReportingServiceProxy::SetTelemetryCustomProperties()
0x8d0b  ldarg.0
0x8d0c  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass25_0::<>4__this
0x8d11  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x8d16  ldarg.0
0x8d17  ldfld    string <>c__DisplayClass25_0::ItemPath
0x8d1c  ldarg.0
0x8d1d  ldfld    string <>c__DisplayClass25_0::HistoryID
0x8d22  ldarg.0
0x8d23  ldfld    bool <>c__DisplayClass25_0::ForRendering
0x8d28  ldarg.0
0x8d29  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue[] <>c__DisplayClass25_0::Values
0x8d2e  ldarg.0
0x8d2f  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials[] <>c__DisplayClass25_0::Credentials
0x8d34  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[] [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010::GetItemParameters(string, string, bool, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue[], class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials[])
0x8d39  ret
```
