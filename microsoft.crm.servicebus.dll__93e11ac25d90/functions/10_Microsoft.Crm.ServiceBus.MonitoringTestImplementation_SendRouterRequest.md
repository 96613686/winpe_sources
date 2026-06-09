# Microsoft.Crm.ServiceBus.MonitoringTestImplementation::SendRouterRequest

- ea: `0x10`
- end: `0x92`
- name: `Microsoft.Crm.ServiceBus.MonitoringTestImplementation::SendRouterRequest`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0xc0`
- `0x460`
- `0x4c0`
- `0x19c0`
- `0x1aa0`
- `0x1ac0`
- `0x1ae0`
- `0x1b00`
- `0x1b20`
- `0x1b60`
- `0x1b80`
- `0x1ba0`
- `0x1bc0`

## pseudocode

```c

```

## disassembly

```asm
0x10  ldarg.1
0x11  ldstr    aSolutionnamesp// "solutionNamespace"
0x16  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1b  ldarg.2
0x1c  ldstr    aPath// "path"
0x21  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x26  newobj   instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::.ctor()
0x2b  stloc.0
0x2c  ldloc.0
0x2d  ldarg.1
0x2e  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_SolutionName(string value)
0x33  ldloc.0
0x34  ldarg.2
0x35  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_Path(string value)
0x3a  ldloc.0
0x3b  ldsfld   string [System]System.Uri::UriSchemeHttps
0x40  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_Scheme(string value)
0x45  ldloc.0
0x46  ldc.i4.1
0x47  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_ValidateOnly(bool value)
0x4c  ldloc.0
0x4d  ldsfld   string [mscorlib]System.String::Empty
0x52  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_UserInfo(string value)
0x57  ldloc.0
0x58  ldsfld   string [mscorlib]System.String::Empty
0x5d  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_InitiatingUserInfo(string value)
0x62  ldloc.0
0x63  ldc.i4.1
0x64  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_Contract(valuetype ContractType value)
0x69  ldloc.0
0x6a  ldc.i4.0
0x6b  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_IsFederatedMode(bool value)
0x70  ldloc.0
0x71  ldstr    aCrmtest// "crmtest"
0x76  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_OrganizationName(string value)
0x7b  call     class Microsoft.Crm.ServiceBus.IRouterClientManager Microsoft.Crm.ServiceBus.RouterClientManager::get_Current()
0x80  callvirt instance class Microsoft.Crm.ServiceBus.IRouterClient Microsoft.Crm.ServiceBus.IRouterClientManager::RetrieveReadyClient()
0x85  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::.ctor()
0x8a  ldloc.0
0x8b  callvirt instance string Microsoft.Crm.ServiceBus.IRouterClient::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context, class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo)
0x90  pop
0x91  ret
```
