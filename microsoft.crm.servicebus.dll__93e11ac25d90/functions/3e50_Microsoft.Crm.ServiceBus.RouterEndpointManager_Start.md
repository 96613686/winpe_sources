# Microsoft.Crm.ServiceBus.RouterEndpointManager::Start

- ea: `0x3e50`
- end: `0x3e5c`
- name: `Microsoft.Crm.ServiceBus.RouterEndpointManager::Start`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1720`
- `0x3e60`

## pseudocode

```c

```

## disassembly

```asm
0x3e50  call     void Microsoft.Crm.ServiceBus.PerformanceCounters::Install()
0x3e55  ldarg.0
0x3e56  call     instance void Microsoft.Crm.ServiceBus.RouterEndpointManager::StartRouterService()
0x3e5b  ret
```
