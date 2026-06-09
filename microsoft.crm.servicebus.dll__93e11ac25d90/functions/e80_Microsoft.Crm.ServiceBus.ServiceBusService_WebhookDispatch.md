# Microsoft.Crm.ServiceBus.ServiceBusService::WebhookDispatch

- ea: `0xe80`
- end: `0xf4b`
- name: `Microsoft.Crm.ServiceBus.ServiceBusService::WebhookDispatch`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xbb0`

## callees

- `0xe80`
- `0xfe0`
- `0x1d30`
- `0x1d50`
- `0x66c0`

## string_xrefs

- `0xeda`: `The Webhook post is disabled for the organization. OrgId:{0}, serviceEndpointId: {1}, name: {2}`

## pseudocode

```c

```

## disassembly

```asm
0xe80  ldc.i4.1
0xe81  stloc.0
0xe82  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xe87  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xe8c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_WebhookEndpoint()
0xe91  ldarg.2
0xe92  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0xe97  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xe9c  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xea1  stloc.0
0xea2  leave.s  loc_ED7
0xea4  stloc.2
0xea5  ldloc.2
0xea6  ldarg.2
0xea7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0xeac  ldc.i4.s 0x40
0xeae  ldstr    aHitExceptionWh// "Hit exception when trying to fetch FCB "...
0xeb3  ldc.i4.2
0xeb4  newarr   [mscorlib]System.Object
0xeb9  dup
0xeba  ldc.i4.0
0xebb  ldarg.2
0xebc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0xec1  box      [mscorlib]System.Guid
0xec6  stelem.ref
0xec7  dup
0xec8  ldc.i4.1
0xec9  ldloc.2
0xeca  callvirt instance string [mscorlib]System.Object::ToString()
0xecf  stelem.ref
0xed0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xed5  leave.s  loc_ED7
0xed7  ldloc.0
0xed8  brtrue.s loc_F08
0xeda  ldstr    aTheWebhookPost// "The Webhook post is disabled for the or"...
0xedf  ldarg.2
0xee0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0xee5  box      [mscorlib]System.Guid
0xeea  ldarg.1
0xeeb  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_ServiceEndpointId()
0xef0  ldarg.1
0xef1  callvirt instance string Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Name()
0xef6  call     string [mscorlib]System.String::Format(string, object, object, object)
0xefb  ldc.i4   0x80050206
0xf00  ldc.i4.s 0x40
0xf02  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory)
0xf07  throw
0xf08  ldnull
0xf09  stloc.1
0xf0a  ldsfld   class Microsoft.Crm.ServiceBus.IWebhookClient Microsoft.Crm.ServiceBus.ServiceBusService::_WebhookClient
0xf0f  ldarg.1
0xf10  ldarg.2
0xf11  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext Microsoft.Crm.ServiceBus.ServiceBusService::ConvertToRemoteExecutionContext(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context)
0xf16  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.Crm.ServiceBus.IWebhookClient::PostAsync(class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context)
0xf1b  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<string>::get_Result()
0xf20  stloc.1
0xf21  leave.s  loc_F49
0xf23  stloc.3
0xf24  ldloc.3
0xf25  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception> [mscorlib]System.AggregateException::get_InnerExceptions()
0xf2a  brfalse.s loc_F47
0xf2c  ldloc.3
0xf2d  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception> [mscorlib]System.AggregateException::get_InnerExceptions()
0xf32  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception>::get_Count()
0xf37  ldc.i4.1
0xf38  bne.un.s loc_F47
0xf3a  ldloc.3
0xf3b  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception> [mscorlib]System.AggregateException::get_InnerExceptions()
0xf40  ldc.i4.0
0xf41  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [mscorlib]System.Exception>::get_Item(!!T0)
0xf46  throw
0xf47  rethrow
0xf49  ldloc.1
0xf4a  ret
```
