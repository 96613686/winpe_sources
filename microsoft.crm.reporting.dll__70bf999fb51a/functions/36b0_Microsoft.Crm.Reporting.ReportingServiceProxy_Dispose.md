# Microsoft.Crm.Reporting.ReportingServiceProxy::Dispose

- ea: `0x36b0`
- end: `0x36bc`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::Dispose`
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
0x36b0  ldarg.0
0x36b1  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x36b6  callvirt instance void [System]System.ComponentModel.Component::Dispose()
0x36bb  ret
```
