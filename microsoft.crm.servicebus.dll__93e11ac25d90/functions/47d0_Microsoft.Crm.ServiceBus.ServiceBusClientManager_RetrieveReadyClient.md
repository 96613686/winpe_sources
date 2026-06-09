# Microsoft.Crm.ServiceBus.ServiceBusClientManager::RetrieveReadyClient

- ea: `0x47d0`
- end: `0x47fe`
- name: `Microsoft.Crm.ServiceBus.ServiceBusClientManager::RetrieveReadyClient`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x4120`

## callees

- `0x1bb0`
- `0x4500`
- `0x46f0`
- `0x47d0`

## string_xrefs

- `0x47e3`: `servicebusclient`

## pseudocode

```c

```

## disassembly

```asm
0x47d0  ldarg.0
0x47d1  ldstr    aEndpointinfo// "endpointInfo"
0x47d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x47db  ldarg.0
0x47dc  call     class Microsoft.Crm.ServiceBus.ServiceBusClientBase Microsoft.Crm.ServiceBus.ServiceBusClientFactory::CreateClient(class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo)
0x47e1  stloc.0
0x47e2  ldloc.0
0x47e3  ldstr    aServicebusclie// "servicebusclient"
0x47e8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x47ed  ldarg.0
0x47ee  callvirt instance bool Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_ValidateOnly()
0x47f3  brtrue.s loc_47FC
0x47f5  ldloc.0
0x47f6  ldarg.0
0x47f7  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::Start(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x47fc  ldloc.0
0x47fd  ret
```
