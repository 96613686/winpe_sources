# Microsoft.Crm.ServiceBus.RouterClientInProc::Execute

- ea: `0x420`
- end: `0x42d`
- name: `Microsoft.Crm.ServiceBus.RouterClientInProc::Execute`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x4120`
- `0x43f0`

## pseudocode

```c

```

## disassembly

```asm
0x420  newobj   instance void Microsoft.Crm.ServiceBus.RouterService::.ctor()
0x425  ldarg.1
0x426  ldarg.2
0x427  callvirt instance string Microsoft.Crm.ServiceBus.RouterService::ExecuteInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context, class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo)
0x42c  ret
```
