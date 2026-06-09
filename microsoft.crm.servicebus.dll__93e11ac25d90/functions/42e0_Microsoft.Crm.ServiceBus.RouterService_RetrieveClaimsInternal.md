# Microsoft.Crm.ServiceBus.RouterService::RetrieveClaimsInternal

- ea: `0x42e0`
- end: `0x42ed`
- name: `Microsoft.Crm.ServiceBus.RouterService::RetrieveClaimsInternal`
- size: `13`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x430`
- `0x4090`

## callees

- `0x5590`
- `0x5750`

## pseudocode

```c

```

## disassembly

```asm
0x42e0  ldarg.1
0x42e1  newobj   instance void Microsoft.Crm.ServiceBus.TokenProvider::.ctor(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x42e6  ldc.i4.0
0x42e7  callvirt instance string Microsoft.Crm.ServiceBus.TokenProvider::RetrieveTokenString(bool fromServiceBusScope)
0x42ec  ret
```
