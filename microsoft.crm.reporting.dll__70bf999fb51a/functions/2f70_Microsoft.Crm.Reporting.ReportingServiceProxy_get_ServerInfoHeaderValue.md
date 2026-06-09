# Microsoft.Crm.Reporting.ReportingServiceProxy::get_ServerInfoHeaderValue

- ea: `0x2f70`
- end: `0x2f7c`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::get_ServerInfoHeaderValue`
- size: `12`
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
0x2f70  ldarg.0
0x2f71  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x2f76  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ServerInfoHeader [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010::get_ServerInfoHeaderValue()
0x2f7b  ret
```
