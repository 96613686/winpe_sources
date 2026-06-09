# Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::DeliverPromote

- ea: `0x33950`
- end: `0x33ed8`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::DeliverPromote`
- size: `1416`
- prototype: ``
- caller_count: `0`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x30660`
- `0x32680`
- `0x326e0`
- `0x32970`
- `0x32980`
- `0x32a00`
- `0x32d90`
- `0x335a0`
- `0x33630`
- `0x33950`
- `0x35770`
- `0x357f0`
- `0x35800`
- `0x35820`
- `0x35830`
- `0x368c0`
- `0x369b0`
- `0x369c0`
- `0x369e0`
- `0x40cc0`
- `0x41800`
- `0x41850`
- `0x41a20`
- `0x4da80`
- `0x4e480`
- `0x4e870`
- `0x4f250`
- `0x4f410`
- `0x50210`
- `0x50b40`
- `0x516f0`
- `0x71c40`
- `0x71ff0`
- `0x814f0`
- `0x81500`
- `0x81640`

## string_xrefs

- `0x339d3`: `Server-Side Synchronization (Incoming): Items Discarded`
- `0x33e54`: `Server-Side Synchronization (Incoming): Items Discarded`
- `0x339dd`: `Server-Side Synchronization (Incoming): Items Discarded Throughput`
- `0x33e5e`: `Server-Side Synchronization (Incoming): Items Discarded Throughput`
- `0x339e7`: `Server-Side Synchronization (Incoming): Items Failed`
- `0x33ead`: `Server-Side Synchronization (Incoming): Items Failed`
- `0x339f1`: `Server-Side Synchronization (Incoming): Items Failed Throughput`
- `0x33eb7`: `Server-Side Synchronization (Incoming): Items Failed Throughput`
- `0x33a16`: `This item has already been processed. Skip`
- `0x33ae4`: `Mailbox: {0} - Error in DeliverPromote with non XML characters removed. Exception: {1}`
- `0x33bb0`: `Mailbox: {0} - Exception occurred while delivering email message in CRM with non XML characters removed. Exception : {1}`
- `0x33c0a`: `Couldn't remove item from IncomingEmailMessageIdCache.InstanceForManualEmail cache while delivering promote email message failed. Mailbox: {0}`
- `0x33c50`: `Mailbox: {0} - Created Email Activity (id = {1}) for message {2}.`
- `0x33ca0`: `Server-Side Synchronization (Incoming): Emails Delivered`
- `0x33caa`: `Server-Side Synchronization (Incoming): Items Delivered Throughput`

## pseudocode

```c

```

## disassembly

```asm
0x33950  ldarg.1
0x33951  ldstr    aExchangeemailm// "ExchangeEmailMessage"
0x33956  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3395b  ldarg.0
0x3395c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x33961  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::set_DeliveredEmailCrmId(valuetype [mscorlib]System.Guid value)
0x33966  ldarg.0
0x33967  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_InfoLevelPayload()
0x3396c  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsRetrieved
0x33971  ldarg.0
0x33972  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_InfoLevelPayload()
0x33977  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsRetrieved
0x3397c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::ContainsKey(var<u1>)
0x33981  brtrue.s loc_3398B
0x33983  ldc.i4.1
0x33984  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x33989  br.s     loc_339B1
0x3398b  ldarg.0
0x3398c  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_InfoLevelPayload()
0x33991  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsRetrieved
0x33996  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::get_Item(void)
0x3399b  callvirt instance string [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat::ToString()
0x339a0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x339a5  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x339aa  ldc.i4.1
0x339ab  add
0x339ac  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x339b1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::set_Item(var<u1>, !!T0)
0x339b6  call     class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::get_InstanceForManualEmail()
0x339bb  ldarg.1
0x339bc  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x339c1  ldarg.0
0x339c2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x339c7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x339cc  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::TryAddItem(string MessageID, valuetype [mscorlib]System.Guid OrganizationID)
0x339d1  brtrue.s loc_33A2D
0x339d3  ldstr    aServerSideSync_6// "Server-Side Synchronization (Incoming):"...
0x339d8  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x339dd  ldstr    aServerSideSync_7// "Server-Side Synchronization (Incoming):"...
0x339e2  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x339e7  ldstr    aServerSideSync_8// "Server-Side Synchronization (Incoming):"...
0x339ec  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x339f1  ldstr    aServerSideSync_9// "Server-Side Synchronization (Incoming):"...
0x339f6  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x339fb  ldarg.1
0x339fc  isinst   Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage
0x33a01  brfalse.s loc_33A0F
0x33a03  ldarg.1
0x33a04  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage
0x33a09  ldc.i4.1
0x33a0a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeEmailMessage::set_ProcessResult(int32 value)
0x33a0f  ldarg.0
0x33a10  ldarg.0
0x33a11  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::syncResponseFactory
0x33a16  ldstr    aThisItemHasAlr// "This item has already been processed. S"...
0x33a1b  ldc.i4.0
0x33a1c  ldc.i4.0
0x33a1d  ldstr    asc_8A7C2// ""
0x33a22  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetSuccessSyncResponse(string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeTypeInCrm, [opt] int32 traceCode, [opt] string traceCodeString)
0x33a27  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x33a2c  ret
0x33a2d  ldarg.1
0x33a2e  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x33a33  stloc.0
0x33a34  ldarg.1
0x33a35  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_Subject()
0x33a3a  stloc.1
0x33a3b  ldarg.1
0x33a3c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x33a41  stloc.2
0x33a42  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x33a47  stloc.3
0x33a48  ldnull
0x33a49  stloc.s  4
0x33a4b  ldc.i4.0
0x33a4c  stloc.s  5
0x33a4e  ldarg.0
0x33a4f  ldarg.1
0x33a50  ldc.i4.0
0x33a51  call     instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverPromoteEmailResponse Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::ExecuteDeliverPromoteEmailRequest(class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage exchangeEmailMessage, [opt] bool filterNonXml)
0x33a56  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverPromoteEmailResponse::get_EmailId()
0x33a5b  stloc.3
0x33a5c  ldc.i4.1
0x33a5d  stloc.s  5
0x33a5f  leave    loc_33C37
0x33a64  stloc.s  6
0x33a66  ldloc.s  6
0x33a68  stloc.s  4
0x33a6a  ldarg.0
0x33a6b  ldc.i4.2
0x33a6c  ldstr    aMailbox0Except_1// "Mailbox: {0} - Exception in DeliverProm"...
0x33a71  ldc.i4.2
0x33a72  newarr   [mscorlib]System.Object
0x33a77  dup
0x33a78  ldc.i4.0
0x33a79  ldarg.0
0x33a7a  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x33a7f  ldstr    aMailboxid// "mailboxid"
0x33a84  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x33a89  stelem.ref
0x33a8a  dup
0x33a8b  ldc.i4.1
0x33a8c  ldloc.s  6
0x33a8e  ldarg.0
0x33a8f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x33a94  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x33a99  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x33a9e  stelem.ref
0x33a9f  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x33aa4  ldloc.s  6
0x33aa6  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x33aab  stloc.s  7
0x33aad  ldloc.s  7
0x33aaf  brfalse  loc_33BEA
0x33ab4  ldc.i4   0x80040278
0x33ab9  ldloc.s  7
0x33abb  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x33ac0  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x33ac5  bne.un   loc_33BEA
0x33aca  ldarg.0
0x33acb  ldarg.1
0x33acc  ldc.i4.1
0x33acd  call     instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverPromoteEmailResponse Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::ExecuteDeliverPromoteEmailRequest(class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage exchangeEmailMessage, [opt] bool filterNonXml)
0x33ad2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.DeliverPromoteEmailResponse::get_EmailId()
0x33ad7  stloc.3
0x33ad8  ldc.i4.1
0x33ad9  stloc.s  5
0x33adb  leave    loc_33BEA
0x33ae0  stloc.s  8
0x33ae2  ldarg.0
0x33ae3  ldc.i4.1
0x33ae4  ldstr    aMailbox0ErrorI// "Mailbox: {0} - Error in DeliverPromote "...
0x33ae9  ldc.i4.2
0x33aea  newarr   [mscorlib]System.Object
0x33aef  dup
0x33af0  ldc.i4.0
0x33af1  ldarg.0
0x33af2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x33af7  ldstr    aMailboxid// "mailboxid"
0x33afc  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x33b01  stelem.ref
0x33b02  dup
0x33b03  ldc.i4.1
0x33b04  ldloc.s  8
0x33b06  ldarg.0
0x33b07  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x33b0c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x33b11  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x33b16  stelem.ref
0x33b17  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x33b1c  leave    loc_33BEA
0x33b21  stloc.s  9
0x33b23  ldloc.s  9
0x33b25  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x33b2a  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x33b2f  stloc.s  0xA
0x33b31  ldsfld   string [mscorlib]System.String::Empty
0x33b36  stloc.s  0xB
0x33b38  ldloc.s  9
0x33b3a  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x33b3f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ErrorDetailCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorDetails()
0x33b44  ldstr    aCallstack// "CallStack"
0x33b49  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x33b4e  brfalse.s loc_33B6D
0x33b50  ldloc.s  9
0x33b52  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x33b57  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ErrorDetailCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorDetails()
0x33b5c  ldstr    aCallstack// "CallStack"
0x33b61  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x33b66  isinst   [mscorlib]System.String
0x33b6b  stloc.s  0xB
0x33b6d  ldarg.0
0x33b6e  ldc.i4.1
0x33b6f  ldstr    aMailbox0ErrorI_0// "Mailbox: {0} - Error in DeliverPromote."...
0x33b74  ldc.i4.3
0x33b75  newarr   [mscorlib]System.Object
0x33b7a  dup
0x33b7b  ldc.i4.0
0x33b7c  ldarg.0
0x33b7d  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x33b82  ldstr    aMailboxid// "mailboxid"
0x33b87  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x33b8c  stelem.ref
0x33b8d  dup
0x33b8e  ldc.i4.1
0x33b8f  ldloca.s 0xA
0x33b91  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x33b96  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x33b9b  stelem.ref
0x33b9c  dup
0x33b9d  ldc.i4.2
0x33b9e  ldloc.s  0xB
0x33ba0  stelem.ref
0x33ba1  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x33ba6  leave.s  loc_33BEA
0x33ba8  stloc.s  0xC
0x33baa  ldloc.s  0xC
0x33bac  stloc.s  4
0x33bae  ldarg.0
0x33baf  ldc.i4.1
0x33bb0  ldstr    aMailbox0Except_2// "Mailbox: {0} - Exception occurred while"...
0x33bb5  ldc.i4.2
0x33bb6  newarr   [mscorlib]System.Object
0x33bbb  dup
0x33bbc  ldc.i4.0
0x33bbd  ldarg.0
0x33bbe  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x33bc3  ldstr    aMailboxid// "mailboxid"
0x33bc8  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x33bcd  stelem.ref
0x33bce  dup
0x33bcf  ldc.i4.1
0x33bd0  ldloc.s  0xC
0x33bd2  ldarg.0
0x33bd3  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x33bd8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x33bdd  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x33be2  stelem.ref
0x33be3  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x33be8  leave.s  loc_33BEA
0x33bea  leave.s  loc_33C37
0x33bec  ldloc.s  5
0x33bee  brtrue.s loc_33C2D
0x33bf0  call     class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::get_InstanceForManualEmail()
0x33bf5  ldloc.0
0x33bf6  ldarg.0
0x33bf7  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x33bfc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x33c01  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::TryRemoveItem(string MessageId, valuetype [mscorlib]System.Guid OrganizationId)
0x33c06  brtrue.s loc_33C2D
0x33c08  ldarg.0
0x33c09  ldc.i4.2
0x33c0a  ldstr    aCouldnTRemoveI// "Couldn't remove item from IncomingEmail"...
0x33c0f  ldc.i4.1
0x33c10  newarr   [mscorlib]System.Object
0x33c15  dup
0x33c16  ldc.i4.0
0x33c17  ldarg.0
0x33c18  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x33c1d  ldstr    aMailboxid// "mailboxid"
0x33c22  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x33c27  stelem.ref
0x33c28  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x33c2d  ldarg.1
0x33c2e  brfalse.s loc_33C36
0x33c30  ldarg.1
0x33c31  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33c36  endfinally
0x33c37  ldloc.3
0x33c38  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x33c3d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x33c42  brfalse  loc_33D63
0x33c47  ldarg.0
0x33c48  ldloc.3
0x33c49  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::set_DeliveredEmailCrmId(valuetype [mscorlib]System.Guid value)
0x33c4e  ldarg.0
0x33c4f  ldc.i4.4
0x33c50  ldstr    aMailbox0Create// "Mailbox: {0} - Created Email Activity ("...
0x33c55  ldc.i4.3
0x33c56  newarr   [mscorlib]System.Object
0x33c5b  dup
0x33c5c  ldc.i4.0
0x33c5d  ldarg.0
0x33c5e  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x33c63  ldstr    aMailboxid// "mailboxid"
0x33c68  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x33c6d  stelem.ref
0x33c6e  dup
0x33c6f  ldc.i4.1
0x33c70  ldloc.3
0x33c71  box      [mscorlib]System.Guid
0x33c76  stelem.ref
0x33c77  dup
0x33c78  ldc.i4.2
0x33c79  ldloc.0
0x33c7a  stelem.ref
0x33c7b  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x33c80  ldarg.0
0x33c81  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x33c86  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x33c8b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::GetMailboxData()
0x33c90  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OwnerId()
0x33c95  stloc.s  0xD
0x33c97  ldarg.0
0x33c98  ldloc.3
0x33c99  ldloc.s  0xD
0x33c9b  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::ExecuteAssignRequest(valuetype [mscorlib]System.Guid emailId, valuetype [mscorlib]System.Guid userId)
0x33ca0  ldstr    aServerSideSync_10// "Server-Side Synchronization (Incoming):"...
0x33ca5  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x33caa  ldstr    aServerSideSync_11// "Server-Side Synchronization (Incoming):"...
0x33caf  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x33cb4  ldarg.0
0x33cb5  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_InfoLevelPayload()
0x33cba  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsDelivered
0x33cbf  ldarg.0
0x33cc0  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_InfoLevelPayload()
0x33cc5  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsDelivered
0x33cca  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::ContainsKey(var<u1>)
0x33ccf  brtrue.s loc_33CD9
0x33cd1  ldc.i4.1
  ... truncated ...
```
