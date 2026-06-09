# Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::SendEventData

- ea: `0x4fb0`
- end: `0x50d9`
- name: `Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::SendEventData`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x4f10`

## callees

- `0x1490`
- `0x14b0`
- `0x14d0`
- `0x4820`
- `0x4870`
- `0x4fb0`
- `0x52c0`
- `0x52e0`
- `0x5300`
- `0x5400`
- `0x5460`

## string_xrefs

- `0x509a`: `Start sending event data in ServiceBusBrokeredMessageClient`
- `0x50c1`: `End sending event data in ServiceBusBrokeredMessageClient`

## pseudocode

```c

```

## disassembly

```asm
0x4fb0  ldarg.0
0x4fb1  ldarg.1
0x4fb2  call     instance class [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.EventData Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::CreateEventData(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context)
0x4fb7  stloc.0
0x4fb8  ldloc.0
0x4fb9  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.EventData::get_Properties()
0x4fbe  ldsfld   string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ClaimTypes::Organization
0x4fc3  ldarg.0
0x4fc4  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_EndPointInfo()
0x4fc9  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_OrganizationName()
0x4fce  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x4fd3  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x4fd8  ldloc.0
0x4fd9  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.EventData::get_Properties()
0x4fde  ldsfld   string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ClaimTypes::User
0x4fe3  ldarg.0
0x4fe4  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_EndPointInfo()
0x4fe9  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_UserInfo()
0x4fee  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x4ff3  ldloc.0
0x4ff4  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.EventData::get_Properties()
0x4ff9  ldsfld   string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ClaimTypes::InitiatingUser
0x4ffe  ldarg.0
0x4fff  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_EndPointInfo()
0x5004  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_InitiatingUserInfo()
0x5009  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x500e  ldloc.0
0x500f  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.EventData::get_Properties()
0x5014  ldsfld   string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ClaimTypes::EntityLogicalName
0x5019  ldarg.1
0x501a  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_PrimaryEntityName()
0x501f  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5024  ldloc.0
0x5025  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.EventData::get_Properties()
0x502a  ldsfld   string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ClaimTypes::RequestName
0x502f  ldarg.1
0x5030  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_MessageName()
0x5035  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x503a  ldloc.0
0x503b  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.EventData::get_Properties()
0x5040  ldstr    aContenttype// "ContentType"
0x5045  ldarg.0
0x5046  call     instance string Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::MessageContentType()
0x504b  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5050  ldloc.0
0x5051  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.EventData::get_Properties()
0x5056  ldstr    aCorrelationid// "CorrelationId"
0x505b  ldarg.1
0x505c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_CorrelationId()
0x5061  stloc.2
0x5062  ldloca.s 2
0x5064  ldstr    aB// "B"
0x5069  call     instance string [mscorlib]System.Guid::ToString(string)
0x506e  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5073  ldarg.0
0x5074  call     instance class Microsoft.Crm.ServiceBus.IMessagingFactory Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_MessagingFactory()
0x5079  ldarg.0
0x507a  call     instance string Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_EntityPath()
0x507f  callvirt instance class Microsoft.Crm.ServiceBus.IEventDataSender Microsoft.Crm.ServiceBus.IMessagingFactory::CreateEventDataSender(string entityPath)
0x5084  stloc.1
0x5085  ldarg.1
0x5086  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x508b  ldc.i4.s 0x2F
0x508d  ldstr    a0// "{0}"
0x5092  ldc.i4.1
0x5093  newarr   [mscorlib]System.Object
0x5098  dup
0x5099  ldc.i4.0
0x509a  ldstr    aStartSendingEv// "Start sending event data in ServiceBusB"...
0x509f  stelem.ref
0x50a0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x50a5  ldloc.1
0x50a6  ldloc.0
0x50a7  callvirt instance void Microsoft.Crm.ServiceBus.IEventDataSender::Send(class [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.EventData message)
0x50ac  ldarg.1
0x50ad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x50b2  ldc.i4.s 0x2F
0x50b4  ldstr    a0// "{0}"
0x50b9  ldc.i4.1
0x50ba  newarr   [mscorlib]System.Object
0x50bf  dup
0x50c0  ldc.i4.0
0x50c1  ldstr    aEndSendingEven// "End sending event data in ServiceBusBro"...
0x50c6  stelem.ref
0x50c7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x50cc  leave.s  loc_50D8
0x50ce  ldloc.0
0x50cf  brfalse.s loc_50D7
0x50d1  ldloc.0
0x50d2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x50d7  endfinally
0x50d8  ret
```
