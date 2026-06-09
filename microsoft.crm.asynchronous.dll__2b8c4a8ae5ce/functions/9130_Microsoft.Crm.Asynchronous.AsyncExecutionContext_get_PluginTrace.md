# Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_PluginTrace

- ea: `0x9130`
- end: `0x9150`
- name: `Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_PluginTrace`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x5830`

## callees

- `0x90e0`
- `0x9300`

## pseudocode

```c

```

## disassembly

```asm
0x9130  ldarg.0
0x9131  call     instance class [mscorlib]System.IServiceProvider Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_ServiceProvider()
0x9136  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ITracingService
0x913b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9140  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x9145  isinst   Microsoft.Crm.Asynchronous.AsyncTracingService
0x914a  callvirt instance string Microsoft.Crm.Asynchronous.AsyncTracingService::get_TraceInfo()
0x914f  ret
```
