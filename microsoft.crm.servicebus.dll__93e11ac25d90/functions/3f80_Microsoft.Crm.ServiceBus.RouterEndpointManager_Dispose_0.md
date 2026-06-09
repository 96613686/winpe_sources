# Microsoft.Crm.ServiceBus.RouterEndpointManager::Dispose_0

- ea: `0x3f80`
- end: `0x3f9f`
- name: `Microsoft.Crm.ServiceBus.RouterEndpointManager::Dispose_0`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x3f70`

## callees

- `0x17b0`
- `0x3f30`
- `0x3f80`

## pseudocode

```c

```

## disassembly

```asm
0x3f80  ldarg.0
0x3f81  ldfld    bool Microsoft.Crm.ServiceBus.RouterEndpointManager::_disposed
0x3f86  brfalse.s loc_3F89
0x3f88  ret
0x3f89  ldarg.1
0x3f8a  brfalse.s loc_3F97
0x3f8c  call     void Microsoft.Crm.ServiceBus.PerformanceCounters::Uninstall()
0x3f91  ldarg.0
0x3f92  call     instance void Microsoft.Crm.ServiceBus.RouterEndpointManager::StopRouterService()
0x3f97  ldarg.0
0x3f98  ldc.i4.1
0x3f99  stfld    bool Microsoft.Crm.ServiceBus.RouterEndpointManager::_disposed
0x3f9e  ret
```
