# <>c__DisplayClass37_0::<MoveItem>b__0

- ea: `0x9100`
- end: `0x9128`
- name: `<>c__DisplayClass37_0::<MoveItem>b__0`
- size: `40`
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
0x9100  ldarg.0
0x9101  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass37_0::<>4__this
0x9106  call     instance void Microsoft.Crm.Reporting.ReportingServiceProxy::SetTelemetryCustomProperties()
0x910b  ldarg.0
0x910c  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass37_0::<>4__this
0x9111  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x9116  ldarg.0
0x9117  ldfld    string <>c__DisplayClass37_0::ItemPath
0x911c  ldarg.0
0x911d  ldfld    string <>c__DisplayClass37_0::Target
0x9122  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010::MoveItem(string, string)
0x9127  ret
```
