# Microsoft.Crm.Reporting.ReportingServiceProxy::set_ServerInfoHeaderValue

- ea: `0x2f80`
- end: `0x2f8d`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::set_ServerInfoHeaderValue`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2f60`

## pseudocode

```c

```

## disassembly

```asm
0x2f80  ldarg.0
0x2f81  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x2f86  ldarg.1
0x2f87  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010::set_ServerInfoHeaderValue(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ServerInfoHeader)
0x2f8c  ret
```
