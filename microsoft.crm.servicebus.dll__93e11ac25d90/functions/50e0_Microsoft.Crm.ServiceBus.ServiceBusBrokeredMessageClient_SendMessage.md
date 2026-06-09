# Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::SendMessage

- ea: `0x50e0`
- end: `0x5250`
- name: `Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::SendMessage`
- size: `368`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x4f10`

## callees

- `0x1430`
- `0x1490`
- `0x14b0`
- `0x14d0`
- `0x2820`
- `0x4810`
- `0x4850`
- `0x50e0`
- `0x52c0`
- `0x52e0`
- `0x5300`
- `0x5380`
- `0x5400`
- `0x5cd0`

## string_xrefs

- `0x5211`: `Start sending message data in ServiceBusBrokeredMessageClient`
- `0x5238`: `End sending message data in ServiceBusBrokeredMessageClient`

## pseudocode

```c

```

## disassembly

```asm
0x50e0  ldarg.1
0x50e1  ldc.i4   0x30000
0x50e6  conv.i8
0x50e7  ldarg.0
0x50e8  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_EndPointInfo()
0x50ed  ldloca.s 0
0x50ef  call     bool Microsoft.Crm.ServiceBus.ServiceBusUtility::TryHandleMaxMessageSize(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context, int64 maxMessageSize, class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo, [out] string& serializedContext)
0x50f4  stloc.1
0x50f5  ldarg.0
0x50f6  ldarg.1
0x50f7  call     instance class [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.BrokeredMessage Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::CreateBrokeredMessageInstance(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context)
0x50fc  stloc.2
0x50fd  ldloc.2
0x50fe  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.BrokeredMessage::get_Properties()
0x5103  ldsfld   string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ClaimTypes::Organization
0x5108  ldarg.0
0x5109  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_EndPointInfo()
0x510e  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_OrganizationName()
0x5113  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x5118  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x511d  ldloc.2
0x511e  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.BrokeredMessage::get_Properties()
0x5123  ldsfld   string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ClaimTypes::User
0x5128  ldarg.0
0x5129  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_EndPointInfo()
0x512e  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_UserInfo()
0x5133  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5138  ldloc.2
0x5139  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.BrokeredMessage::get_Properties()
0x513e  ldsfld   string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ClaimTypes::InitiatingUser
0x5143  ldarg.0
0x5144  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_EndPointInfo()
0x5149  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_InitiatingUserInfo()
0x514e  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5153  ldloc.2
0x5154  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.BrokeredMessage::get_Properties()
0x5159  ldsfld   string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ClaimTypes::EntityLogicalName
0x515e  ldarg.1
0x515f  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_PrimaryEntityName()
0x5164  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x5169  ldloc.2
0x516a  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.BrokeredMessage::get_Properties()
0x516f  ldsfld   string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ClaimTypes::RequestName
0x5174  ldarg.1
0x5175  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_MessageName()
0x517a  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x517f  ldloc.2
0x5180  ldarg.0
0x5181  call     instance string Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::MessageContentType()
0x5186  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.BrokeredMessage::set_ContentType(string)
0x518b  ldarg.0
0x518c  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_EndPointInfo()
0x5191  callvirt instance bool Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_IsFederatedMode()
0x5196  brfalse.s loc_51B7
0x5198  ldarg.0
0x5199  call     T0x2B000006
0x519e  stloc.s  4
0x51a0  ldloc.2
0x51a1  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.BrokeredMessage::get_Properties()
0x51a6  ldsfld   string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ClaimTypes::SecurityToken
0x51ab  ldloc.s  4
0x51ad  callvirt instance string Microsoft.Crm.ServiceBus.TokenPusher::get_Token()
0x51b2  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x51b7  ldloc.2
0x51b8  ldarg.1
0x51b9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_CorrelationId()
0x51be  stloc.s  5
0x51c0  ldloca.s 5
0x51c2  ldstr    aB// "B"
0x51c7  call     instance string [mscorlib]System.Guid::ToString(string)
0x51cc  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.BrokeredMessage::set_CorrelationId(string)
0x51d1  ldloc.1
0x51d2  brfalse.s loc_51EA
0x51d4  ldloc.2
0x51d5  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.BrokeredMessage::get_Properties()
0x51da  ldsfld   string Microsoft.Crm.ServiceBus.ServiceBusUtility::MessageMaxSizeExceeded
0x51df  ldc.i4.1
0x51e0  box      [mscorlib]System.Boolean
0x51e5  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x51ea  ldarg.0
0x51eb  call     instance class Microsoft.Crm.ServiceBus.IMessagingFactory Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_MessagingFactory()
0x51f0  ldarg.0
0x51f1  call     instance string Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::get_EntityPath()
0x51f6  callvirt instance class Microsoft.Crm.ServiceBus.IMessageSender Microsoft.Crm.ServiceBus.IMessagingFactory::CreateMessageSender(string entityPath)
0x51fb  stloc.3
0x51fc  ldarg.1
0x51fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x5202  ldc.i4.s 0x2F
0x5204  ldstr    a0// "{0}"
0x5209  ldc.i4.1
0x520a  newarr   [mscorlib]System.Object
0x520f  dup
0x5210  ldc.i4.0
0x5211  ldstr    aStartSendingMe// "Start sending message data in ServiceBu"...
0x5216  stelem.ref
0x5217  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x521c  ldloc.3
0x521d  ldloc.2
0x521e  callvirt instance void Microsoft.Crm.ServiceBus.IMessageSender::Send(class [Microsoft.ServiceBus]Microsoft.ServiceBus.Messaging.BrokeredMessage message)
0x5223  ldarg.1
0x5224  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext::get_OrganizationId()
0x5229  ldc.i4.s 0x2F
0x522b  ldstr    a0// "{0}"
0x5230  ldc.i4.1
0x5231  newarr   [mscorlib]System.Object
0x5236  dup
0x5237  ldc.i4.0
0x5238  ldstr    aEndSendingMess// "End sending message data in ServiceBusB"...
0x523d  stelem.ref
0x523e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5243  leave.s  loc_524F
0x5245  ldloc.2
0x5246  brfalse.s loc_524E
0x5248  ldloc.2
0x5249  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x524e  endfinally
0x524f  ret
```
