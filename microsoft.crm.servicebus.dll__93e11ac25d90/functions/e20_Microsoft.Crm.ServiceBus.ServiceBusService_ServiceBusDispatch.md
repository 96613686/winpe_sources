# Microsoft.Crm.ServiceBus.ServiceBusService::ServiceBusDispatch

- ea: `0xe20`
- end: `0xe77`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::ServiceBusDispatch`
- size: `87`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xbb0`

## callees

- `0xc0`
- `0x460`
- `0x4c0`
- `0xe20`
- `0xfe0`

## string_xrefs

- `0xe35`: `ServiceBusDispatch`
- `0xe3a`: `D:\a\1\s\src\Shared\ServiceBus\Client\ServiceBusService.cs`
- `0xe50`: `Sending outbound messages using Azure AppFabric component has been disabled for this organization, Please contact your system administrator for more information.`

## pseudocode

```c

```

## disassembly

```asm
0xe20  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0xe25  ldarg.2
0xe26  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0xe2b  ldstr    aDisableappfabr// "DisableAppFabricPost"
0xe30  ldc.i4   0x122
0xe35  ldstr    aServicebusdisp// "ServiceBusDispatch"
0xe3a  ldstr    aDA1SSrcSharedS// "D:\\a\\1\\s\\src\\Shared\\ServiceBus\\C"...
0xe3f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0xe44  stloc.0
0xe45  ldloc.0
0xe46  brfalse.s loc_E60
0xe48  ldloc.0
0xe49  unbox.any [mscorlib]System.Boolean
0xe4e  brfalse.s loc_E60
0xe50  ldstr    aSendingOutboun// "Sending outbound messages using Azure A"...
0xe55  ldc.i4   0x8004417A
0xe5a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xe5f  throw
0xe60  call     class Microsoft.Crm.ServiceBus.IRouterClientManager Microsoft.Crm.ServiceBus.RouterClientManager::get_Current()
0xe65  callvirt instance class Microsoft.Crm.ServiceBus.IRouterClient Microsoft.Crm.ServiceBus.IRouterClientManager::RetrieveReadyClient()
0xe6a  ldarg.2
0xe6b  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext Microsoft.Crm.ServiceBus.ServiceBusService::ConvertToRemoteExecutionContext(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0xe70  ldarg.1
0xe71  callvirt instance string Microsoft.Crm.ServiceBus.IRouterClient::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context, class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo)
0xe76  ret
```
