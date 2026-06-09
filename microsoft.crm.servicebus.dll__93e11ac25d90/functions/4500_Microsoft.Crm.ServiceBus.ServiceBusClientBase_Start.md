# Microsoft.Crm.ServiceBus.ServiceBusClientBase::Start

- ea: `0x4500`
- end: `0x4534`
- name: `Microsoft.Crm.ServiceBus.ServiceBusClientBase::Start`
- size: `52`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x47d0`
- `0x4980`
- `0x4b50`
- `0x4d10`
- `0x4e40`

## callees

- `0x1630`
- `0x4540`
- `0x4550`
- `0x4560`
- `0x4640`
- `0x4660`
- `0x4680`

## pseudocode

```c

```

## disassembly

```asm
0x4500  ldarg.0
0x4501  ldarg.1
0x4502  callvirt instance class [System]System.Uri Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_Address()
0x4507  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_EndpointUri(class [System]System.Uri value)
0x450c  ldarg.0
0x450d  ldarg.0
0x450e  ldarg.1
0x450f  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress Microsoft.Crm.ServiceBus.ServiceBusClientBase::RetrieveEndpointAddress(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x4514  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_ServiceEndpointAddress(class [System.ServiceModel]System.ServiceModel.EndpointAddress value)
0x4519  ldarg.0
0x451a  ldarg.0
0x451b  ldarg.1
0x451c  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding Microsoft.Crm.ServiceBus.ServiceBusClientBase::RetrieveClientBinding(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x4521  call     instance void Microsoft.Crm.ServiceBus.ServiceBusClientBase::set_EndpointBinding(class [System.ServiceModel]System.ServiceModel.Channels.Binding value)
0x4526  ldarg.0
0x4527  ldarg.0
0x4528  ldarg.1
0x4529  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> Microsoft.Crm.ServiceBus.ServiceBusClientBase::RetrieveClientBehavior(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x452e  stfld    class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> Microsoft.Crm.ServiceBus.ServiceBusClientBase::endpointBehaviors
0x4533  ret
```
