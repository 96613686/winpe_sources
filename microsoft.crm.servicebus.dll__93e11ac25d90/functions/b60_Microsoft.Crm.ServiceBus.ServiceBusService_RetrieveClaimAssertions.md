# Microsoft.Crm.ServiceBus.ServiceBusService::RetrieveClaimAssertions

- ea: `0xb60`
- end: `0xba2`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::RetrieveClaimAssertions`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0xd0`
- `0x460`
- `0x4c0`
- `0xf50`
- `0x1ae0`
- `0x1b20`
- `0x1ca0`

## string_xrefs

- `0xb62`: `serviceendpoint`

## pseudocode

```c

```

## disassembly

```asm
0xb60  ldarg.0
0xb61  ldarg.1
0xb62  ldstr    aServiceendpoin// "serviceendpoint"
0xb67  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb6c  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0xb71  call     instance class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation Microsoft.Crm.ServiceBus.ServiceBusService::RetrieveEndpointInfo(string assemblyName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference serviceEndpoint)
0xb76  stloc.0
0xb77  ldloc.0
0xb78  ldarg.2
0xb79  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0xb7e  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_Path(string value)
0xb83  ldloc.0
0xb84  ldarg.3
0xb85  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_ClaimCollection(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> value)
0xb8a  ldloc.0
0xb8b  ldc.i4.0
0xb8c  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_Contract(valuetype ContractType value)
0xb91  call     class Microsoft.Crm.ServiceBus.IRouterClientManager Microsoft.Crm.ServiceBus.RouterClientManager::get_Current()
0xb96  callvirt instance class Microsoft.Crm.ServiceBus.IRouterClient Microsoft.Crm.ServiceBus.IRouterClientManager::RetrieveReadyClient()
0xb9b  ldloc.0
0xb9c  callvirt instance string Microsoft.Crm.ServiceBus.IRouterClient::RetrieveClaims(class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo)
0xba1  ret
```
