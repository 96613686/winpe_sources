# Microsoft.Crm.ServiceBus.RouterEndpointManager::Dispose

- ea: `0x3f70`
- end: `0x3f7e`
- name: `Microsoft.Crm.ServiceBus.RouterEndpointManager::Dispose`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x3f80`

## pseudocode

```c

```

## disassembly

```asm
0x3f70  ldarg.0
0x3f71  ldc.i4.1
0x3f72  call     instance void Microsoft.Crm.ServiceBus.RouterEndpointManager::Dispose(bool disposing)
0x3f77  ldarg.0
0x3f78  call     void [mscorlib]System.GC::SuppressFinalize(object)
0x3f7d  ret
```
