# Microsoft.Crm.ServiceBus.EventDataSender::.ctor

- ea: `0x3df0`
- end: `0x3e0c`
- name: `Microsoft.Crm.ServiceBus.EventDataSender::.ctor`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x48d0`

## callees

- `0x3df0`

## pseudocode

```c

```

## disassembly

```asm
0x3df0  ldarg.0
0x3df1  call     instance void [mscorlib]System.Object::.ctor()
0x3df6  ldarg.1
0x3df7  brtrue.s loc_3E04
0x3df9  ldstr    aEventHubClient// "Event Hub client cannot be null."
0x3dfe  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x3e03  throw
0x3e04  ldarg.0
0x3e05  ldarg.1
0x3e06  stfld    class [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.EventHubClient Microsoft.Crm.ServiceBus.EventDataSender::_eventHubClient
0x3e0b  ret
```
