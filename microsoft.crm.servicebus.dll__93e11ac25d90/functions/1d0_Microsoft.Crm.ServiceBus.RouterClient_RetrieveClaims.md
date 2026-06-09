# Microsoft.Crm.ServiceBus.RouterClient::RetrieveClaims

- ea: `0x1d0`
- end: `0x1ed`
- name: `Microsoft.Crm.ServiceBus.RouterClient::RetrieveClaims`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1870`

## pseudocode

```c

```

## disassembly

```asm
0x1d0  ldarg.0
0x1d1  ldfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x1d6  ldstr    aRouterchannel// "RouterChannel"
0x1db  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1e0  ldarg.0
0x1e1  ldfld    class Microsoft.Crm.ServiceBus.IRouterChannel Microsoft.Crm.ServiceBus.RouterClient::channel
0x1e6  ldarg.1
0x1e7  callvirt instance string Microsoft.Crm.ServiceBus.IRouterContract::RetrieveClaims(class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo)
0x1ec  ret
```
