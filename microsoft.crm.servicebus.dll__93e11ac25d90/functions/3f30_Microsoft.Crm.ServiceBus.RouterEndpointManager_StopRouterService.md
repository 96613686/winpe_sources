# Microsoft.Crm.ServiceBus.RouterEndpointManager::StopRouterService

- ea: `0x3f30`
- end: `0x3f66`
- name: `Microsoft.Crm.ServiceBus.RouterEndpointManager::StopRouterService`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3f80`

## callees

- `0x3f30`

## pseudocode

```c

```

## disassembly

```asm
0x3f30  ldarg.0
0x3f31  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost Microsoft.Crm.ServiceBus.RouterEndpointManager::host
0x3f36  brfalse.s loc_3F65
0x3f38  ldarg.0
0x3f39  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost Microsoft.Crm.ServiceBus.RouterEndpointManager::host
0x3f3e  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.CommunicationState [System.ServiceModel]System.ServiceModel.Channels.CommunicationObject::get_State()
0x3f43  ldc.i4.5
0x3f44  bne.un.s loc_3F53
0x3f46  ldarg.0
0x3f47  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost Microsoft.Crm.ServiceBus.RouterEndpointManager::host
0x3f4c  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.CommunicationObject::Abort()
0x3f51  br.s     loc_3F5E
0x3f53  ldarg.0
0x3f54  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost Microsoft.Crm.ServiceBus.RouterEndpointManager::host
0x3f59  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.CommunicationObject::Close()
0x3f5e  ldarg.0
0x3f5f  ldnull
0x3f60  stfld    class [System.ServiceModel]System.ServiceModel.ServiceHost Microsoft.Crm.ServiceBus.RouterEndpointManager::host
0x3f65  ret
```
