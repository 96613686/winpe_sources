# Microsoft.Crm.Reporting.ReportingServiceProxy::get_Credentials

- ea: `0x2fb0`
- end: `0x2fbc`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::get_Credentials`
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
0x2fb0  ldarg.0
0x2fb1  call     instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ReportingService2010 Microsoft.Crm.Reporting.ReportingServiceProxy::get_ReportingService()
0x2fb6  callvirt instance class [System]System.Net.ICredentials [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::get_Credentials()
0x2fbb  ret
```
