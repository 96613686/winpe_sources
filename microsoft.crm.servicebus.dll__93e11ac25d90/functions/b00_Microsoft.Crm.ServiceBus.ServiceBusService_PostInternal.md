# Microsoft.Crm.ServiceBus.ServiceBusService::PostInternal

- ea: `0xb00`
- end: `0xb59`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::PostInternal`
- size: `89`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x6d0`
- `0x7b0`
- `0x870`
- `0xaf0`

## callees

- `0xb00`
- `0xbb0`
- `0xf50`
- `0x1bc0`

## string_xrefs

- `0xb25`: `serviceEndpoint`
- `0xb35`: `serviceEndpoint.Id`

## pseudocode

```c

```

## disassembly

```asm
0xb00  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xb05  ldstr    aPostponeappfab// "PostponeAppFabricRequestsInMinutes"
0xb0a  ldc.i4.0
0xb0b  callvirt T0x2B000002
0xb10  ldc.i4.0
0xb11  ble.s    loc_B24
0xb13  ldc.i4   0x80044179
0xb18  ldc.i4.0
0xb19  newarr   [mscorlib]System.Object
0xb1e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xb23  throw
0xb24  ldarg.2
0xb25  ldstr    aServiceendpoin_0// "serviceEndpoint"
0xb2a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xb2f  ldarg.2
0xb30  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0xb35  ldstr    aServiceendpoin_1// "serviceEndpoint.Id"
0xb3a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xb3f  ldarg.0
0xb40  ldarg.1
0xb41  ldarg.2
0xb42  call     instance class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation Microsoft.Crm.ServiceBus.ServiceBusService::RetrieveEndpointInfo(string assemblyName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference serviceEndpoint)
0xb47  stloc.0
0xb48  ldloc.0
0xb49  ldarg.3
0xb4a  callvirt instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_ValidateOnly(bool value)
0xb4f  ldarg.0
0xb50  ldloc.0
0xb51  ldarg.s  4
0xb53  call     instance string Microsoft.Crm.ServiceBus.ServiceBusService::Dispatch(class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0xb58  ret
```
