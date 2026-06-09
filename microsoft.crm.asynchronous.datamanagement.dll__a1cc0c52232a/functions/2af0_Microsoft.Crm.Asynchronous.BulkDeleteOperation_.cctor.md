# Microsoft.Crm.Asynchronous.BulkDeleteOperation::.cctor

- ea: `0x2af0`
- end: `0x2b0f`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::.cctor`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2af0  call     class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmLoggerFactory::get_LoggerFactory()
0x2af5  ldtoken  Microsoft.Crm.Asynchronous.BulkDeleteOperation
0x2afa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2aff  callvirt instance string [mscorlib]System.Type::get_FullName()
0x2b04  callvirt instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILoggerFactory::CreateLogger(string)
0x2b09  stsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.BulkDeleteOperation::Logger
0x2b0e  ret
```
