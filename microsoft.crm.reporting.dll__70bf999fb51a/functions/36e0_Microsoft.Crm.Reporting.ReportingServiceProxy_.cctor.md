# Microsoft.Crm.Reporting.ReportingServiceProxy::.cctor

- ea: `0x36e0`
- end: `0x3709`
- name: `Microsoft.Crm.Reporting.ReportingServiceProxy::.cctor`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x36e0  ldtoken  Microsoft.Crm.Reporting.ReportingServiceProxy
0x36e5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x36ea  callvirt instance string [mscorlib]System.Type::get_FullName()
0x36ef  stsfld   string Microsoft.Crm.Reporting.ReportingServiceProxy::ClassFullName
0x36f4  call     class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmLoggerFactory::get_LoggerFactory()
0x36f9  ldsfld   string Microsoft.Crm.Reporting.ReportingServiceProxy::ClassFullName
0x36fe  callvirt instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory::CreateLogger(string)
0x3703  stsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Reporting.ReportingServiceProxy::Logger
0x3708  ret
```
