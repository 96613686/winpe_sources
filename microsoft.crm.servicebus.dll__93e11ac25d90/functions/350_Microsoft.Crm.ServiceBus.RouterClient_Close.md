# Microsoft.Crm.ServiceBus.RouterClient::Close

- ea: `0x350`
- end: `0x38c`
- name: `Microsoft.Crm.ServiceBus.RouterClient::Close`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x110`
- `0x570`

## callees

- `0x350`

## pseudocode

```c

```

## disassembly

```asm
0x350  ldarg.0
0x351  ldfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x356  brfalse.s loc_37E
0x358  ldarg.0
0x359  ldfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x35e  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.CommunicationState [System.ServiceModel]System.ServiceModel.ICommunicationObject::get_State()
0x363  ldc.i4.5
0x364  bne.un.s loc_373
0x366  ldarg.0
0x367  ldfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x36c  callvirt instance void [System.ServiceModel]System.ServiceModel.ICommunicationObject::Abort()
0x371  br.s     loc_37E
0x373  ldarg.0
0x374  ldfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x379  callvirt instance void [System.ServiceModel]System.ServiceModel.ICommunicationObject::Close()
0x37e  leave.s  loc_38B
0x380  pop
0x381  leave.s  loc_38B
0x383  ldarg.0
0x384  ldnull
0x385  stfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x38a  endfinally
0x38b  ret
```
