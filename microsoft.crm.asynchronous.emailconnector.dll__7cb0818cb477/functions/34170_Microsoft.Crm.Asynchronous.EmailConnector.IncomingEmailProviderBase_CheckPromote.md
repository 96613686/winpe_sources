# Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::CheckPromote

- ea: `0x34170`
- end: `0x346a2`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::CheckPromote`
- size: `1330`
- prototype: ``
- caller_count: `0`
- callee_count: `39`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0xacf0`
- `0x30660`
- `0x32680`
- `0x326e0`
- `0x32970`
- `0x32980`
- `0x32a00`
- `0x32d90`
- `0x32dd0`
- `0x32e50`
- `0x33480`
- `0x33ee0`
- `0x340f0`
- `0x34170`
- `0x35770`
- `0x35800`
- `0x35830`
- `0x368c0`
- `0x36960`
- `0x369b0`
- `0x369c0`
- `0x369e0`
- `0x40cc0`
- `0x41800`
- `0x41850`
- `0x41a20`
- `0x41a30`
- `0x41a40`
- `0x41a60`
- `0x41a80`
- `0x41aa0`
- `0x4e480`
- `0x4e870`
- `0x4f250`
- `0x4f410`
- `0x516f0`
- `0x71ff0`
- `0x814f0`
- `0x81500`

## string_xrefs

- `0x341b3`: `Server-Side Synchronization (Incoming): Items Discarded`
- `0x3462f`: `Server-Side Synchronization (Incoming): Items Discarded`
- `0x341bd`: `Server-Side Synchronization (Incoming): Items Discarded Throughput`
- `0x34639`: `Server-Side Synchronization (Incoming): Items Discarded Throughput`
- `0x341c7`: `Server-Side Synchronization (Incoming): Items Failed`
- `0x34645`: `Server-Side Synchronization (Incoming): Items Failed`
- `0x341d1`: `Server-Side Synchronization (Incoming): Items Failed Throughput`
- `0x3464f`: `Server-Side Synchronization (Incoming): Items Failed Throughput`
- `0x3423f`: `IncomingEmail discarded since the item is found in IncomingEmailMessageIdCache. Id:{0}, Mailbox:{1}`
- `0x342a5`: `Couldn't remove item from IncomingEmailMessageIdCache.InstanceForManualEmail cache while the email does not exist in Crm from CheckPromote call. Mailbox: {0}`
- `0x34338`: `CheckPromote with NonXml char filter`

## pseudocode

```c

```

## disassembly

```asm
0x34170  ldarg.1
0x34171  ldstr    aEmailmessage// "EmailMessage"
0x34176  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3417b  call     class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::get_InstanceForManualEmail()
0x34180  ldarg.1
0x34181  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x34186  ldarg.0
0x34187  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x3418c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x34191  ldarg.2
0x34192  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::Contains(string MessageID, valuetype [mscorlib]System.Guid OrganizationID, [out] valuetype [mscorlib]System.Guid& CrmId)
0x34197  brfalse  loc_342C8
0x3419c  ldarg.0
0x3419d  ldarg.2
0x3419e  constrained. [mscorlib]System.Guid
0x341a4  callvirt instance string [mscorlib]System.Object::ToString()
0x341a9  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::RetrieveEmailEntity(string crmId)
0x341ae  brfalse  loc_34286
0x341b3  ldstr    aServerSideSync_6// "Server-Side Synchronization (Incoming):"...
0x341b8  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x341bd  ldstr    aServerSideSync_7// "Server-Side Synchronization (Incoming):"...
0x341c2  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x341c7  ldstr    aServerSideSync_8// "Server-Side Synchronization (Incoming):"...
0x341cc  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x341d1  ldstr    aServerSideSync_9// "Server-Side Synchronization (Incoming):"...
0x341d6  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x341db  ldarg.0
0x341dc  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_InfoLevelPayload()
0x341e1  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsRetrieved
0x341e6  ldarg.0
0x341e7  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_InfoLevelPayload()
0x341ec  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsRetrieved
0x341f1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::ContainsKey(var<u1>)
0x341f6  brtrue.s loc_34200
0x341f8  ldc.i4.1
0x341f9  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x341fe  br.s     loc_34226
0x34200  ldarg.0
0x34201  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_InfoLevelPayload()
0x34206  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsRetrieved
0x3420b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::get_Item(void)
0x34210  callvirt instance string [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat::ToString()
0x34215  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3421a  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x3421f  ldc.i4.1
0x34220  add
0x34221  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x34226  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::set_Item(var<u1>, !!T0)
0x3422b  ldarg.1
0x3422c  isinst   Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage
0x34231  brfalse.s loc_3423F
0x34233  ldarg.1
0x34234  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage
0x34239  ldc.i4.1
0x3423a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage::set_ProcessResult(int32 value)
0x3423f  ldstr    aIncomingemailD// "IncomingEmail discarded since the item "...
0x34244  ldarg.1
0x34245  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x3424a  ldarg.0
0x3424b  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x34250  ldstr    aMailboxid// "mailboxid"
0x34255  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3425a  call     string [mscorlib]System.String::Format(string, object, object)
0x3425f  stloc.s  4
0x34261  ldarg.0
0x34262  ldc.i4.3
0x34263  ldloc.s  4
0x34265  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x3426a  ldarg.0
0x3426b  ldarg.0
0x3426c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::syncResponseFactory
0x34271  ldloc.s  4
0x34273  ldc.i4.0
0x34274  ldc.i4.0
0x34275  ldstr    asc_8A7C2// ""
0x3427a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetSuccessSyncResponse(string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeTypeInCrm, [opt] int32 traceCode, [opt] string traceCodeString)
0x3427f  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x34284  ldc.i4.0
0x34285  ret
0x34286  call     class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::get_InstanceForManualEmail()
0x3428b  ldarg.1
0x3428c  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x34291  ldarg.0
0x34292  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x34297  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3429c  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::TryRemoveItem(string MessageId, valuetype [mscorlib]System.Guid OrganizationId)
0x342a1  brtrue.s loc_342C8
0x342a3  ldarg.0
0x342a4  ldc.i4.2
0x342a5  ldstr    aCouldnTRemoveI_0// "Couldn't remove item from IncomingEmail"...
0x342aa  ldc.i4.1
0x342ab  newarr   [mscorlib]System.Object
0x342b0  dup
0x342b1  ldc.i4.0
0x342b2  ldarg.0
0x342b3  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x342b8  ldstr    aMailboxid// "mailboxid"
0x342bd  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x342c2  stelem.ref
0x342c3  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x342c8  ldc.i4.0
0x342c9  stloc.0
0x342ca  ldc.i4.m1
0x342cb  stloc.1
0x342cc  ldc.i4.m1
0x342cd  stloc.2
0x342ce  ldnull
0x342cf  stloc.3
0x342d0  ldarg.0
0x342d1  ldarg.1
0x342d2  ldc.i4.0
0x342d3  call     instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckPromoteEmailResponse Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::ExecuteCheckPromoteEmailRequest(class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage exchangeEmailMessage, [opt] bool filterNonXml)
0x342d8  stloc.3
0x342d9  ldloc.3
0x342da  callvirt instance int32 [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckPromoteEmailResponse::get_ReasonCode()
0x342df  stloc.1
0x342e0  ldloc.3
0x342e1  callvirt instance bool [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckPromoteEmailResponse::get_ShouldPromote()
0x342e6  stloc.0
0x342e7  leave.s  loc_34347
0x342e9  stloc.s  5
0x342eb  ldarg.0
0x342ec  ldloc.s  5
0x342ee  ldc.i4.2
0x342ef  ldstr    aCheckpromote// "CheckPromote"
0x342f4  ldc.i4.1
0x342f5  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::ProcessException(class [mscorlib]System.Exception e, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string errorMessage, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeType)
0x342fa  ldloc.s  5
0x342fc  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x34301  stloc.s  6
0x34303  ldloc.s  6
0x34305  brfalse.s loc_34345
0x34307  ldc.i4   0x80040278
0x3430c  ldloc.s  6
0x3430e  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x34313  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x34318  bne.un.s loc_34345
0x3431a  ldarg.0
0x3431b  ldarg.1
0x3431c  ldc.i4.1
0x3431d  call     instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckPromoteEmailResponse Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::ExecuteCheckPromoteEmailRequest(class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage exchangeEmailMessage, [opt] bool filterNonXml)
0x34322  stloc.3
0x34323  ldloc.3
0x34324  callvirt instance int32 [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckPromoteEmailResponse::get_ReasonCode()
0x34329  stloc.1
0x3432a  ldloc.3
0x3432b  callvirt instance bool [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckPromoteEmailResponse::get_ShouldPromote()
0x34330  stloc.0
0x34331  leave.s  loc_34345
0x34333  pop
0x34334  ldarg.0
0x34335  ldloc.s  5
0x34337  ldc.i4.1
0x34338  ldstr    aCheckpromoteWi// "CheckPromote with NonXml char filter"
0x3433d  ldc.i4.0
0x3433e  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::ProcessException(class [mscorlib]System.Exception e, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string errorMessage, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeType)
0x34343  leave.s  loc_34345
0x34345  leave.s  loc_34347
0x34347  ldtoken  Microsoft.Crm.Asynchronous.EmailConnector.PromoteDecision
0x3434c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x34351  ldloc.1
0x34352  box      [mscorlib]System.Int32
0x34357  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x3435c  brfalse.s loc_34360
0x3435e  ldloc.1
0x3435f  stloc.2
0x34360  ldloc.0
0x34361  brfalse.s loc_343A6
0x34363  ldarg.0
0x34364  ldc.i4.4
0x34365  ldstr    aMailbox0Messag// "Mailbox: {0} - Message {1} verification"...
0x3436a  ldc.i4.3
0x3436b  newarr   [mscorlib]System.Object
0x34370  dup
0x34371  ldc.i4.0
0x34372  ldarg.0
0x34373  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x34378  ldstr    aMailboxid// "mailboxid"
0x3437d  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x34382  stelem.ref
0x34383  dup
0x34384  ldc.i4.1
0x34385  ldarg.1
0x34386  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x3438b  stelem.ref
0x3438c  dup
0x3438d  ldc.i4.2
0x3438e  ldloca.s 2
0x34390  constrained. Microsoft.Crm.Asynchronous.EmailConnector.PromoteDecision
0x34396  callvirt instance string [mscorlib]System.Object::ToString()
0x3439b  stelem.ref
0x3439c  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x343a1  br       loc_346A0
0x343a6  ldloc.2
0x343a7  brtrue   loc_3444D
0x343ac  ldarg.0
0x343ad  ldarg.1
0x343ae  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x343b3  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x343b8  ldloca.s 7
0x343ba  ldloca.s 8
0x343bc  ldloca.s 9
0x343be  ldloca.s 0xA
0x343c0  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::RetrieveDuplicate(string messageId, [out] string& emailId, [out] string& regardingObjectId, [out] int32& regardingObjectType, [out] string& regardingObjectName)
0x343c5  ldloc.s  7
0x343c7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x343cc  brtrue.s loc_3442A
0x343ce  ldarg.1
0x343cf  ldloc.s  7
0x343d1  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::set_CrmId(string value)
0x343d6  ldarg.1
0x343d7  ldloc.s  8
0x343d9  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::set_RegardingId(string value)
0x343de  ldarg.1
0x343df  ldloc.s  9
0x343e1  conv.i8
0x343e2  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::set_RegardingObjectTypeCode(int64 value)
0x343e7  ldarg.1
0x343e8  ldloc.s  0xA
0x343ea  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::set_RegardingObjectName(string value)
0x343ef  ldloc.s  7
0x343f1  ldloca.s 0xB
0x343f3  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x343f8  brfalse.s loc_3440F
0x343fa  ldarg.2
0x343fb  ldarg.0
0x343fc  ldloc.s  0xB
0x343fe  dup
0x343ff  stloc.s  0xC
0x34401  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::set_DeliveredEmailCrmId(valuetype [mscorlib]System.Guid value)
0x34406  ldloc.s  0xC
0x34408  stobj    [mscorlib]System.Guid
0x3440d  br.s     loc_3442A
0x3440f  ldarg.0
0x34410  ldc.i4.1
0x34411  ldstr    aPassedCrmid0Is// "Passed CrmId {0} is not in guid format"
0x34416  ldc.i4.1
0x34417  newarr   [mscorlib]System.Object
0x3441c  dup
0x3441d  ldc.i4.0
0x3441e  ldarg.1
0x3441f  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_CrmId()
0x34424  stelem.ref
0x34425  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3442a  ldarg.0
0x3442b  ldarg.0
0x3442c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::syncResponseFactory
0x34431  ldstr    aDuplicateFound// "Duplicate found"
0x34436  ldc.i4.0
0x34437  ldloc.1
0x34438  ldloc.1
0x34439  call     string Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::GetErrorStringFromErrorCodeForDeliverPromote(int32 errorCode)
0x3443e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetSuccessSyncResponse(string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeTypeInCrm, [opt] int32 traceCode, [opt] string traceCodeString)
0x34443  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x34448  br       loc_346A0
0x3444d  call     class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::get_InstanceForManualEmail()
0x34452  ldarg.1
0x34453  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x34458  ldarg.0
0x34459  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x3445e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x34463  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::TryAddItem(string MessageID, valuetype [mscorlib]System.Guid OrganizationID)
0x34468  pop
0x34469  ldstr    aMailbox0Messag_0// "Mailbox: {0} - Message verification fai"...
0x3446e  ldarg.0
0x3446f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x34474  ldstr    aMailboxid// "mailboxid"
0x34479  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3447e  ldarg.1
0x3447f  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x34484  ldloca.s 2
0x34486  constrained. Microsoft.Crm.Asynchronous.EmailConnector.PromoteDecision
0x3448c  callvirt instance string [mscorlib]System.Object::ToString()
0x34491  call     string [mscorlib]System.String::Format(string, object, object, object)
0x34496  stloc.s  0xD
0x34498  ldarg.0
0x34499  ldc.i4.4
0x3449a  ldloc.s  0xD
0x3449c  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x344a1  ldarg.0
0x344a2  ldarg.0
0x344a3  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::syncResponseFactory
0x344a8  ldloc.s  0xD
0x344aa  ldc.i4.0
0x344ab  ldloc.1
0x344ac  ldloc.1
0x344ad  call     string Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::GetErrorStringFromErrorCodeForDeliverPromote(int32 errorCode)
0x344b2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetSuccessSyncResponse(string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeTypeInCrm, [opt] int32 traceCode, [opt] string traceCodeString)
0x344b7  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x344bc  ldnull
0x344bd  stloc.s  0xE
0x344bf  ldloc.2
0x344c0  switch   loc_345DC, loc_345DC, loc_34543, loc_345DC, loc_345DC, loc_34543, loc_34543, loc_344E7
0x344e5  br.s     loc_34543
0x344e7  ldarg.0
0x344e8  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x344ed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x344f2  ldc.i4.s 0x1D
0x344f4  ldc.i4.2
0x344f5  ldc.i4.0
  ... truncated ...
```
