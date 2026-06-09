# Microsoft.Crm.ServiceBus.RouterClientInProc::RetrieveClaims

- ea: `0x430`
- end: `0x43c`
- name: `Microsoft.Crm.ServiceBus.RouterClientInProc::RetrieveClaims`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x42e0`
- `0x43f0`

## pseudocode

```c

```

## disassembly

```asm
0x430  newobj   instance void Microsoft.Crm.ServiceBus.RouterService::.ctor()
0x435  ldarg.1
0x436  callvirt instance string Microsoft.Crm.ServiceBus.RouterService::RetrieveClaimsInternal(class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo)
0x43b  ret
```
