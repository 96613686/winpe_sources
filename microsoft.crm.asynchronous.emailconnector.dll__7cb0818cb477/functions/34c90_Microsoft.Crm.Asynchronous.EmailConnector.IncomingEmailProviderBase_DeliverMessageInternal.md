# Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::DeliverMessageInternal

- ea: `0x34c90`
- end: `0x35439`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::DeliverMessageInternal`
- size: `1961`
- prototype: ``
- caller_count: `1`
- callee_count: `48`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x34c70`

## callees

- `0x301e0`
- `0x30280`
- `0x30660`
- `0x30680`
- `0x32680`
- `0x326e0`
- `0x32970`
- `0x32980`
- `0x32a00`
- `0x32d90`
- `0x32dd0`
- `0x34c90`
- `0x35440`
- `0x35770`
- `0x357f0`
- `0x35800`
- `0x35820`
- `0x35830`
- `0x36880`
- `0x369b0`
- `0x369c0`
- `0x369e0`
- `0x40cc0`
- `0x40cd0`
- `0x40e10`
- `0x417f0`
- `0x41800`
- `0x41810`
- `0x41820`
- `0x41830`
- `0x41840`
- `0x41850`
- `0x41860`
- `0x41870`
- `0x41880`
- `0x418d0`
- `0x4da80`
- `0x4e480`
- `0x4e870`
- `0x4f250`
- `0x4f410`
- `0x50210`
- `0x50b40`
- `0x516f0`
- `0x71ff0`
- `0x814f0`
- `0x81500`
- `0x81640`

## string_xrefs

- `0x34d0d`: `Server-Side Synchronization (Incoming): Items Discarded`
- `0x352e4`: `Server-Side Synchronization (Incoming): Items Discarded`
- `0x34d17`: `Server-Side Synchronization (Incoming): Items Discarded Throughput`
- `0x352ee`: `Server-Side Synchronization (Incoming): Items Discarded Throughput`
- `0x34d21`: `Server-Side Synchronization (Incoming): Items Failed`
- `0x3540e`: `Server-Side Synchronization (Incoming): Items Failed`
- `0x34d2b`: `Server-Side Synchronization (Incoming): Items Failed Throughput`
- `0x35418`: `Server-Side Synchronization (Incoming): Items Failed Throughput`
- `0x35195`: `Server-Side Synchronization (Incoming): Emails Delivered`
- `0x3519f`: `Server-Side Synchronization (Incoming): Items Delivered Throughput`
- `0x34d49`: `IncomingEmail discarded since the item is found in IncomingEmailMessageIdCache. Id:{0}, Mailbox:{1}`
- `0x350cc`: `Exception occurred while delivering email message in CRM with non XML characters removed. Exception : {0}`
- `0x35118`: `Couldn't remove item from IncomingEmailMessageIdCache.Instance cache while delivering incoming email message failed. Mailbox: {0}`
- `0x35173`: `Created Email Activity (id = {0}) for message {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x34c90  ldarg.1
0x34c91  ldstr    aEmailmessage// "EmailMessage"
0x34c96  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x34c9b  ldarg.0
0x34c9c  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_InfoLevelPayload()
0x34ca1  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsRetrieved
0x34ca6  ldarg.0
0x34ca7  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_InfoLevelPayload()
0x34cac  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsRetrieved
0x34cb1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::ContainsKey(var<u1>)
0x34cb6  brtrue.s loc_34CC0
0x34cb8  ldc.i4.1
0x34cb9  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x34cbe  br.s     loc_34CE6
0x34cc0  ldarg.0
0x34cc1  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_InfoLevelPayload()
0x34cc6  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsRetrieved
0x34ccb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::get_Item(void)
0x34cd0  callvirt instance string [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat::ToString()
0x34cd5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x34cda  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x34cdf  ldc.i4.1
0x34ce0  add
0x34ce1  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x34ce6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::set_Item(var<u1>, !!T0)
0x34ceb  ldarg.1
0x34cec  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x34cf1  stloc.0
0x34cf2  call     class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::get_Instance()
0x34cf7  ldloc.0
0x34cf8  ldarg.0
0x34cf9  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x34cfe  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x34d03  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::TryAddItem(string MessageID, valuetype [mscorlib]System.Guid OrganizationID)
0x34d08  brtrue   loc_34D8F
0x34d0d  ldstr    aServerSideSync_6// "Server-Side Synchronization (Incoming):"...
0x34d12  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x34d17  ldstr    aServerSideSync_7// "Server-Side Synchronization (Incoming):"...
0x34d1c  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x34d21  ldstr    aServerSideSync_8// "Server-Side Synchronization (Incoming):"...
0x34d26  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x34d2b  ldstr    aServerSideSync_9// "Server-Side Synchronization (Incoming):"...
0x34d30  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x34d35  ldarg.1
0x34d36  isinst   Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage
0x34d3b  brfalse.s loc_34D49
0x34d3d  ldarg.1
0x34d3e  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage
0x34d43  ldc.i4.1
0x34d44  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage::set_ProcessResult(int32 value)
0x34d49  ldstr    aIncomingemailD// "IncomingEmail discarded since the item "...
0x34d4e  ldarg.1
0x34d4f  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x34d54  ldarg.0
0x34d55  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x34d5a  ldstr    aMailboxid// "mailboxid"
0x34d5f  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x34d64  call     string [mscorlib]System.String::Format(string, object, object)
0x34d69  stloc.s  6
0x34d6b  ldarg.0
0x34d6c  ldc.i4.3
0x34d6d  ldloc.s  6
0x34d6f  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x34d74  ldarg.0
0x34d75  ldarg.0
0x34d76  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::syncResponseFactory
0x34d7b  ldloc.s  6
0x34d7d  ldc.i4.0
0x34d7e  ldc.i4.0
0x34d7f  ldstr    asc_8A7C2// ""
0x34d84  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetSuccessSyncResponse(string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeTypeInCrm, [opt] int32 traceCode, [opt] string traceCodeString)
0x34d89  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x34d8e  ret
0x34d8f  ldarg.1
0x34d90  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_TimeReceived()
0x34d95  stloc.s  7
0x34d97  ldloca.s 7
0x34d99  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x34d9e  stloc.1
0x34d9f  ldarg.1
0x34da0  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_TimeReceived()
0x34da5  call     valuetype [mscorlib]System.DateTime [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.DateTimeAttributeMetadata::get_MinSupportedValue()
0x34daa  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x34daf  brtrue.s loc_34DC3
0x34db1  ldarg.1
0x34db2  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_TimeReceived()
0x34db7  call     valuetype [mscorlib]System.DateTime [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.DateTimeAttributeMetadata::get_MaxSupportedValue()
0x34dbc  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x34dc1  brfalse.s loc_34DC9
0x34dc3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x34dc8  stloc.1
0x34dc9  ldarg.0
0x34dca  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x34dcf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x34dd4  ldloca.s 8
0x34dd6  initobj  [mscorlib]System.Guid
0x34ddc  ldloc.s  8
0x34dde  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.Utility::GetCrmService(valuetype [mscorlib]System.Guid organizationId, [opt] valuetype [mscorlib]System.Guid userId)
0x34de3  stloc.2
0x34de4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x34de9  stloc.3
0x34dea  ldnull
0x34deb  stloc.s  4
0x34ded  ldc.i4.0
0x34dee  stloc.s  5
0x34df0  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::.ctor()
0x34df5  stloc.s  9
0x34df7  ldloc.s  9
0x34df9  ldarg.1
0x34dfa  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_Subject()
0x34dff  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x34e04  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_Subject(string)
0x34e09  ldloc.s  9
0x34e0b  ldarg.1
0x34e0c  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_From()
0x34e11  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x34e16  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_From(string)
0x34e1b  ldloc.s  9
0x34e1d  ldarg.1
0x34e1e  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_To()
0x34e23  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x34e28  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_To(string)
0x34e2d  ldloc.s  9
0x34e2f  ldarg.1
0x34e30  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_CC()
0x34e35  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x34e3a  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_Cc(string)
0x34e3f  ldloc.s  9
0x34e41  ldarg.1
0x34e42  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_Bcc()
0x34e47  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x34e4c  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_Bcc(string)
0x34e51  ldloc.s  9
0x34e53  ldarg.1
0x34e54  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x34e59  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x34e5e  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_MessageId(string)
0x34e63  ldloc.s  9
0x34e65  ldloc.1
0x34e66  ldc.i4.1
0x34e67  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x34e6c  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_ReceivedOn(valuetype [mscorlib]System.DateTime)
0x34e71  ldloc.s  9
0x34e73  ldarg.1
0x34e74  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_SubmittedBy()
0x34e79  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x34e7e  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_SubmittedBy(string)
0x34e83  ldloc.s  9
0x34e85  ldarg.1
0x34e86  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_Importance()
0x34e8b  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x34e90  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_Importance(string)
0x34e95  ldloc.s  9
0x34e97  ldarg.1
0x34e98  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_Body()
0x34e9d  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x34ea2  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_Body(string)
0x34ea7  ldloc.s  9
0x34ea9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::.ctor()
0x34eae  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_Attachments(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection)
0x34eb3  ldloc.s  9
0x34eb5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::get_Attachments()
0x34eba  ldstr    aActivitymimeat// "activitymimeattachment"
0x34ebf  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::set_EntityName(string)
0x34ec4  ldloc.s  9
0x34ec6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::get_Attachments()
0x34ecb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x34ed0  ldarg.1
0x34ed1  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity[] Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::GetAttachments()
0x34ed6  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::AddRange(var<u1>[])
0x34edb  ldloc.s  9
0x34edd  ldarg.2
0x34ede  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_ValidateBeforeCreate(bool)
0x34ee3  ldloc.s  9
0x34ee5  ldarg.0
0x34ee6  ldarg.1
0x34ee7  ldloc.s  9
0x34ee9  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::get_From()
0x34eee  ldloc.s  9
0x34ef0  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::get_To()
0x34ef5  ldloc.s  9
0x34ef7  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::get_Cc()
0x34efc  ldloc.s  9
0x34efe  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::get_Bcc()
0x34f03  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::GetExtraProperties(class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage emailMessage, string senderEmailAddress, string toAddress, string ccAddress, string bccAddress)
0x34f08  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_ExtraProperties(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x34f0d  ldloc.2
0x34f0e  ldloc.s  9
0x34f10  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x34f15  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailResponse
0x34f1a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailResponse::get_EmailId()
0x34f1f  stloc.3
0x34f20  ldc.i4.1
0x34f21  stloc.s  5
0x34f23  leave    loc_3515A
0x34f28  stloc.s  0xA
0x34f2a  ldloc.s  0xA
0x34f2c  stloc.s  4
0x34f2e  ldarg.0
0x34f2f  ldc.i4.2
0x34f30  ldstr    aExceptionOccur_5// "Exception occurred while delivering ema"...
0x34f35  ldc.i4.1
0x34f36  newarr   [mscorlib]System.Object
0x34f3b  dup
0x34f3c  ldc.i4.0
0x34f3d  ldloc.s  0xA
0x34f3f  ldarg.0
0x34f40  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x34f45  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x34f4a  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x34f4f  stelem.ref
0x34f50  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x34f55  ldloc.s  0xA
0x34f57  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x34f5c  stloc.s  0xB
0x34f5e  ldloc.s  0xB
0x34f60  brfalse  loc_350F3
0x34f65  ldc.i4   0x80040278
0x34f6a  ldloc.s  0xB
0x34f6c  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x34f71  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x34f76  beq.s    loc_34F8E
0x34f78  ldc.i4   0x80040216
0x34f7d  ldloc.s  0xB
0x34f7f  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x34f84  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x34f89  bne.un   loc_350F3
0x34f8e  nop
0x34f8f  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::.ctor()
0x34f94  stloc.s  0xC
0x34f96  ldloc.s  0xC
0x34f98  ldarg.1
0x34f99  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_Subject()
0x34f9e  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNonXmlCharacters(string source)
0x34fa3  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_Subject(string)
0x34fa8  ldloc.s  0xC
0x34faa  ldarg.1
0x34fab  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_From()
0x34fb0  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNonXmlCharacters(string source)
0x34fb5  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_From(string)
0x34fba  ldloc.s  0xC
0x34fbc  ldarg.1
0x34fbd  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_To()
0x34fc2  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNonXmlCharacters(string source)
0x34fc7  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_To(string)
0x34fcc  ldloc.s  0xC
0x34fce  ldarg.1
0x34fcf  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_CC()
0x34fd4  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNonXmlCharacters(string source)
0x34fd9  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_Cc(string)
0x34fde  ldloc.s  0xC
0x34fe0  ldarg.1
0x34fe1  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_Bcc()
0x34fe6  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNonXmlCharacters(string source)
0x34feb  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_Bcc(string)
0x34ff0  ldloc.s  0xC
0x34ff2  ldarg.1
0x34ff3  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x34ff8  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNonXmlCharacters(string source)
0x34ffd  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_MessageId(string)
0x35002  ldloc.s  0xC
0x35004  ldloc.1
0x35005  ldc.i4.1
0x35006  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x3500b  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_ReceivedOn(valuetype [mscorlib]System.DateTime)
0x35010  ldloc.s  0xC
0x35012  ldarg.1
0x35013  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_SubmittedBy()
0x35018  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNonXmlCharacters(string source)
0x3501d  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_SubmittedBy(string)
0x35022  ldloc.s  0xC
0x35024  ldarg.1
0x35025  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_Importance()
0x3502a  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNonXmlCharacters(string source)
0x3502f  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_Importance(string)
0x35034  ldloc.s  0xC
0x35036  ldarg.1
0x35037  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_Body()
0x3503c  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNonXmlCharacters(string source)
0x35041  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_Body(string)
0x35046  ldloc.s  0xC
0x35048  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::.ctor()
0x3504d  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_Attachments(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection)
0x35052  ldloc.s  0xC
0x35054  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::get_Attachments()
0x35059  ldstr    aActivitymimeat// "activitymimeattachment"
0x3505e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::set_EntityName(string)
0x35063  ldloc.s  0xC
0x35065  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::get_Attachments()
0x3506a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x3506f  ldarg.1
0x35070  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity[] Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::GetAttachments()
0x35075  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::AddRange(var<u1>[])
0x3507a  ldloc.s  0xC
0x3507c  ldarg.2
0x3507d  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverIncomingEmailRequest::set_ValidateBeforeCreate(bool)
0x35082  ldloc.s  0xC
0x35084  ldarg.0
0x35085  ldarg.1
0x35086  ldloc.s  0xC
  ... truncated ...
```
