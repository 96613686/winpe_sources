# Microsoft.Crm.Reporting.ReportingServiceProxy::get_Url

- ea: `0x2f90`
- end: `0x2f9c`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::get_Url`
- size: `12`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x36c0`

## callees

- `0x2f60`

## pseudocode

```c

```

## disassembly

```asm
0x2f90  ldarg.0
0x2f91  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x2f96  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::get_Url()
0x2f9b  ret
```
