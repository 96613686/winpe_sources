# <>c__DisplayClass41_0::<UpdateItemExecutionSnapshot>b__0

- ea: `0x9250`
- end: `0x9272`
- name: `<>c__DisplayClass41_0::<UpdateItemExecutionSnapshot>b__0`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x2f60`
- `0x36c0`

## pseudocode

```c

```

## disassembly

```asm
0x9250  ldarg.0
0x9251  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass41_0::<>4__this
0x9256  call     instance void Microsoft.Crm.Reporting.ReportingServiceProxy::SetTelemetryCustomProperties()
0x925b  ldarg.0
0x925c  ldfld    class Microsoft.Crm.Reporting.ReportingServiceProxy <>c__DisplayClass41_0::<>4__this
0x9261  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x9266  ldarg.0
0x9267  ldfld    string <>c__DisplayClass41_0::ItemPath
0x926c  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010::UpdateItemExecutionSnapshot(string)
0x9271  ret
```
