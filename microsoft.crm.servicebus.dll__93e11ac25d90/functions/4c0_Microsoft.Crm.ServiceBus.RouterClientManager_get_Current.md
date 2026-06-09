# Microsoft.Crm.ServiceBus.RouterClientManager::get_Current

- ea: `0x4c0`
- end: `0x4d7`
- name: `Microsoft.Crm.ServiceBus.RouterClientManager::get_Current`
- size: `23`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x10`
- `0x120`
- `0xb60`
- `0xe20`

## callees

- `0x480`
- `0x4c0`

## pseudocode

```c

```

## disassembly

```asm
0x4c0  ldsfld   class Microsoft.Crm.ServiceBus.IRouterClientManager Microsoft.Crm.ServiceBus.RouterClientManager::selectedStrategyManager
0x4c5  brtrue.s loc_4D1
0x4c7  call     class Microsoft.Crm.ServiceBus.IRouterClientManager Microsoft.Crm.ServiceBus.RouterClientManagerFactory::CreateRouterClientManager()
0x4cc  stsfld   class Microsoft.Crm.ServiceBus.IRouterClientManager Microsoft.Crm.ServiceBus.RouterClientManager::selectedStrategyManager
0x4d1  ldsfld   class Microsoft.Crm.ServiceBus.IRouterClientManager Microsoft.Crm.ServiceBus.RouterClientManager::selectedStrategyManager
0x4d6  ret
```
