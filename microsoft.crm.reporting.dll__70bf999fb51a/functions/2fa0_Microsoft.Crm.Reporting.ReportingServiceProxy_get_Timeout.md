# Microsoft.Crm.Reporting.ReportingServiceProxy::get_Timeout

- ea: `0x2fa0`
- end: `0x2fac`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::get_Timeout`
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
0x2fa0  ldarg.0
0x2fa1  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x2fa6  callvirt instance int32 [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::get_Timeout()
0x2fab  ret
```
