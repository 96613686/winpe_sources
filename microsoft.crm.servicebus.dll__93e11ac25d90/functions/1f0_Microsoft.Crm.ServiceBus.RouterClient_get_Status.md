# Microsoft.Crm.ServiceBus.RouterClient::get_Status

- ea: `0x1f0`
- end: `0x229`
- name: `Microsoft.Crm.ServiceBus.RouterClient::get_Status`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x570`

## callees

- `0x1f0`

## pseudocode

```c

```

## disassembly

```asm
0x1f0  ldarg.0
0x1f1  ldfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x1f6  brfalse.s loc_227
0x1f8  ldarg.0
0x1f9  ldfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x1fe  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.CommunicationState [System.ServiceModel]System.ServiceModel.ICommunicationObject::get_State()
0x203  ldc.i4.2
0x204  bne.un.s loc_208
0x206  ldc.i4.1
0x207  ret
0x208  ldarg.0
0x209  ldfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x20e  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.CommunicationState [System.ServiceModel]System.ServiceModel.ICommunicationObject::get_State()
0x213  brfalse.s loc_223
0x215  ldarg.0
0x216  ldfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x21b  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.CommunicationState [System.ServiceModel]System.ServiceModel.ICommunicationObject::get_State()
0x220  ldc.i4.1
0x221  bne.un.s loc_225
0x223  ldc.i4.0
0x224  ret
0x225  ldc.i4.2
0x226  ret
0x227  ldc.i4.0
0x228  ret
```
