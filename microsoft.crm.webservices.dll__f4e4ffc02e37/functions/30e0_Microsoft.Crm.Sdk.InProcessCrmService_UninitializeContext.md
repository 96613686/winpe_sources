# Microsoft.Crm.Sdk.InProcessCrmService::UninitializeContext

- ea: `0x30e0`
- end: `0x30ee`
- name: `Microsoft.Crm.Sdk.InProcessCrmService::UninitializeContext`
- size: `14`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2e20`
- `0x81b0`

## callees

- `0x3490`

## pseudocode

```c

```

## disassembly

```asm
0x30e0  ldarg.1
0x30e1  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext::EndSoapAndSerializationContexts(class [Microsoft.Crm.Core]Microsoft.Crm.Performance.IWebServicePerformanceCounters)
0x30e6  ldarg.0
0x30e7  ldnull
0x30e8  call     instance void Microsoft.Crm.Sdk.InProcessCrmService::set_RawRequest(object value)
0x30ed  ret
```
