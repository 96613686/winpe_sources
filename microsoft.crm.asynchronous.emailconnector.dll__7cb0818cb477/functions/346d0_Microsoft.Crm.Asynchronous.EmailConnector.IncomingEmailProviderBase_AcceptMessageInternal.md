# Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::AcceptMessageInternal

- ea: `0x346d0`
- end: `0x34c61`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::AcceptMessageInternal`
- size: `1425`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x346b0`

## callees

- `0xacf0`
- `0x32680`
- `0x326e0`
- `0x32970`
- `0x32980`
- `0x32a00`
- `0x32d90`
- `0x32dd0`
- `0x346d0`
- `0x35440`
- `0x35770`
- `0x35830`
- `0x36880`
- `0x36960`
- `0x369b0`
- `0x40cc0`
- `0x40cd0`
- `0x40e10`
- `0x41800`
- `0x41810`
- `0x41820`
- `0x41830`
- `0x41840`
- `0x41850`
- `0x41a20`
- `0x4da80`
- `0x4e480`
- `0x4e870`
- `0x4f250`
- `0x4f410`
- `0x516f0`
- `0x71ff0`
- `0x814f0`
- `0x81500`

## string_xrefs

- `0x34703`: `Server-Side Synchronization (Incoming): Items Discarded`
- `0x34c35`: `Server-Side Synchronization (Incoming): Items Discarded`
- `0x3470d`: `Server-Side Synchronization (Incoming): Items Discarded Throughput`
- `0x34c3f`: `Server-Side Synchronization (Incoming): Items Discarded Throughput`
- `0x34717`: `Server-Side Synchronization (Incoming): Items Failed`
- `0x34c4b`: `Server-Side Synchronization (Incoming): Items Failed`
- `0x34721`: `Server-Side Synchronization (Incoming): Items Failed Throughput`
- `0x34c55`: `Server-Side Synchronization (Incoming): Items Failed Throughput`
- `0x3477b`: `IncomingEmail not accepted since the item is found in IncomingEmailMessageIdCache. Id:{0}, Mailbox:{1}`
- `0x348ac`: `Exception occurred while verifying email message in CRM. Retrying after removing NonXML characters. Exception : {0}`
- `0x349b9`: `Exception occurred while verifying email message in CRM with NonXML characters removed. Exception : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x346d0  ldarg.1
0x346d1  ldstr    aEmailmessage// "EmailMessage"
0x346d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x346db  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x346e0  stloc.0
0x346e1  call     class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::get_Instance()
0x346e6  ldarg.1
0x346e7  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x346ec  ldarg.0
0x346ed  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x346f2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x346f7  ldloca.s 0
0x346f9  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::Contains(string MessageID, valuetype [mscorlib]System.Guid OrganizationID, [out] valuetype [mscorlib]System.Guid& CrmId)
0x346fe  brfalse  loc_347C2
0x34703  ldstr    aServerSideSync_6// "Server-Side Synchronization (Incoming):"...
0x34708  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x3470d  ldstr    aServerSideSync_7// "Server-Side Synchronization (Incoming):"...
0x34712  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x34717  ldstr    aServerSideSync_8// "Server-Side Synchronization (Incoming):"...
0x3471c  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x34721  ldstr    aServerSideSync_9// "Server-Side Synchronization (Incoming):"...
0x34726  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x3472b  ldarg.0
0x3472c  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_InfoLevelPayload()
0x34731  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsRetrieved
0x34736  ldarg.0
0x34737  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_InfoLevelPayload()
0x3473c  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsRetrieved
0x34741  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::ContainsKey(var<u1>)
0x34746  brtrue.s loc_34750
0x34748  ldc.i4.1
0x34749  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x3474e  br.s     loc_34776
0x34750  ldarg.0
0x34751  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat> Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_InfoLevelPayload()
0x34756  ldsfld   string Microsoft.Crm.Asynchronous.EmailConnector.MailboxPayloadPropertyName::EmailConnectorIncomingEmailsRetrieved
0x3475b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::get_Item(void)
0x34760  callvirt instance string [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat::ToString()
0x34765  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3476a  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x3476f  ldc.i4.1
0x34770  add
0x34771  call     class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IntJsonValueFormat [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.TelemetryExtensions::ToJsonValueFormat(int32)
0x34776  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>::set_Item(var<u1>, !!T0)
0x3477b  ldstr    aIncomingemailN// "IncomingEmail not accepted since the it"...
0x34780  ldarg.1
0x34781  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x34786  ldarg.0
0x34787  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x3478c  ldstr    aMailboxid// "mailboxid"
0x34791  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x34796  call     string [mscorlib]System.String::Format(string, object, object)
0x3479b  stloc.s  6
0x3479d  ldarg.0
0x3479e  ldc.i4.3
0x3479f  ldloc.s  6
0x347a1  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x347a6  ldarg.0
0x347a7  ldarg.0
0x347a8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::syncResponseFactory
0x347ad  ldloc.s  6
0x347af  ldc.i4.0
0x347b0  ldc.i4.0
0x347b1  ldstr    asc_8A7C2// ""
0x347b6  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetSuccessSyncResponse(string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeTypeInCrm, [opt] int32 traceCode, [opt] string traceCodeString)
0x347bb  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x347c0  ldc.i4.0
0x347c1  ret
0x347c2  ldarg.0
0x347c3  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x347c8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x347cd  ldloca.s 7
0x347cf  initobj  [mscorlib]System.Guid
0x347d5  ldloc.s  7
0x347d7  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.EmailConnector.Utility::GetCrmService(valuetype [mscorlib]System.Guid organizationId, [opt] valuetype [mscorlib]System.Guid userId)
0x347dc  stloc.1
0x347dd  ldc.i4.0
0x347de  stloc.2
0x347df  ldc.i4.m1
0x347e0  stloc.3
0x347e1  ldc.i4.m1
0x347e2  stloc.s  4
0x347e4  ldnull
0x347e5  stloc.s  5
0x347e7  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::.ctor()
0x347ec  stloc.s  8
0x347ee  ldloc.s  8
0x347f0  ldarg.1
0x347f1  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_Subject()
0x347f6  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x347fb  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::set_Subject(string)
0x34800  ldloc.s  8
0x34802  ldarg.1
0x34803  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_From()
0x34808  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x3480d  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::set_From(string)
0x34812  ldloc.s  8
0x34814  ldarg.1
0x34815  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_To()
0x3481a  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x3481f  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::set_To(string)
0x34824  ldloc.s  8
0x34826  ldarg.1
0x34827  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_CC()
0x3482c  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x34831  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::set_Cc(string)
0x34836  ldloc.s  8
0x34838  ldarg.1
0x34839  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_Bcc()
0x3483e  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x34843  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::set_Bcc(string)
0x34848  ldloc.s  8
0x3484a  ldarg.1
0x3484b  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x34850  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x34855  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::set_MessageId(string)
0x3485a  ldloc.s  8
0x3485c  ldarg.0
0x3485d  ldarg.1
0x3485e  ldloc.s  8
0x34860  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::get_From()
0x34865  ldloc.s  8
0x34867  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::get_To()
0x3486c  ldloc.s  8
0x3486e  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::get_Cc()
0x34873  ldloc.s  8
0x34875  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::get_Bcc()
0x3487a  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::GetExtraProperties(class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage emailMessage, string senderEmailAddress, string toAddress, string ccAddress, string bccAddress)
0x3487f  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::set_ExtraProperties(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x34884  ldloc.1
0x34885  ldloc.s  8
0x34887  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x3488c  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailResponse
0x34891  stloc.s  5
0x34893  ldloc.s  5
0x34895  callvirt instance int32 [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailResponse::get_ReasonCode()
0x3489a  stloc.3
0x3489b  ldloc.s  5
0x3489d  callvirt instance bool [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailResponse::get_ShouldDeliver()
0x348a2  stloc.2
0x348a3  leave    loc_349E2
0x348a8  stloc.s  9
0x348aa  ldarg.0
0x348ab  ldc.i4.2
0x348ac  ldstr    aExceptionOccur_3// "Exception occurred while verifying emai"...
0x348b1  ldc.i4.1
0x348b2  newarr   [mscorlib]System.Object
0x348b7  dup
0x348b8  ldc.i4.0
0x348b9  ldloc.s  9
0x348bb  ldarg.0
0x348bc  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x348c1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x348c6  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x348cb  stelem.ref
0x348cc  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x348d1  ldloc.s  9
0x348d3  isinst   class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>
0x348d8  stloc.s  0xA
0x348da  ldloc.s  0xA
0x348dc  brfalse  loc_349E0
0x348e1  ldc.i4   0x80040278
0x348e6  ldloc.s  0xA
0x348e8  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.FaultException`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationServiceFault>::get_Detail()
0x348ed  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BaseServiceFault::get_ErrorCode()
0x348f2  bne.un   loc_349E0
0x348f7  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::.ctor()
0x348fc  stloc.s  0xB
0x348fe  ldloc.s  0xB
0x34900  ldarg.1
0x34901  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_Subject()
0x34906  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNonXmlCharacters(string source)
0x3490b  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::set_Subject(string)
0x34910  ldloc.s  0xB
0x34912  ldarg.1
0x34913  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_From()
0x34918  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNonXmlCharacters(string source)
0x3491d  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::set_From(string)
0x34922  ldloc.s  0xB
0x34924  ldarg.1
0x34925  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_To()
0x3492a  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNonXmlCharacters(string source)
0x3492f  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::set_To(string)
0x34934  ldloc.s  0xB
0x34936  ldarg.1
0x34937  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_CC()
0x3493c  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNonXmlCharacters(string source)
0x34941  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::set_Cc(string)
0x34946  ldloc.s  0xB
0x34948  ldarg.1
0x34949  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_Bcc()
0x3494e  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNonXmlCharacters(string source)
0x34953  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::set_Bcc(string)
0x34958  ldloc.s  0xB
0x3495a  ldarg.1
0x3495b  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x34960  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNonXmlCharacters(string source)
0x34965  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::set_MessageId(string)
0x3496a  ldloc.s  0xB
0x3496c  ldarg.0
0x3496d  ldarg.1
0x3496e  ldloc.s  0xB
0x34970  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::get_From()
0x34975  ldloc.s  0xB
0x34977  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::get_To()
0x3497c  ldloc.s  0xB
0x3497e  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::get_Cc()
0x34983  ldloc.s  0xB
0x34985  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::get_Bcc()
0x3498a  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::GetExtraProperties(class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage emailMessage, string senderEmailAddress, string toAddress, string ccAddress, string bccAddress)
0x3498f  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailRequest::set_ExtraProperties(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity)
0x34994  ldloc.1
0x34995  ldloc.s  0xB
0x34997  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x3499c  castclass [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailResponse
0x349a1  stloc.s  5
0x349a3  ldloc.s  5
0x349a5  callvirt instance int32 [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailResponse::get_ReasonCode()
0x349aa  stloc.3
0x349ab  ldloc.s  5
0x349ad  callvirt instance bool [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.CheckIncomingEmailResponse::get_ShouldDeliver()
0x349b2  stloc.2
0x349b3  leave.s  loc_349E0
0x349b5  stloc.s  0xC
0x349b7  ldarg.0
0x349b8  ldc.i4.1
0x349b9  ldstr    aExceptionOccur_4// "Exception occurred while verifying emai"...
0x349be  ldc.i4.1
0x349bf  newarr   [mscorlib]System.Object
0x349c4  dup
0x349c5  ldc.i4.0
0x349c6  ldloc.s  0xC
0x349c8  ldarg.0
0x349c9  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x349ce  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x349d3  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x349d8  stelem.ref
0x349d9  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x349de  leave.s  loc_349E0
0x349e0  leave.s  loc_349E2
0x349e2  ldtoken  Microsoft.Crm.Asynchronous.EmailConnector.PromoteDecision
0x349e7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x349ec  ldloc.3
0x349ed  box      [mscorlib]System.Int32
0x349f2  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x349f7  brfalse.s loc_349FC
0x349f9  ldloc.3
0x349fa  stloc.s  4
0x349fc  ldloc.2
0x349fd  brfalse.s loc_34A42
0x349ff  ldarg.0
0x34a00  ldc.i4.4
0x34a01  ldstr    aMessage0Verifi// "Message {0} verification succeeded. Rea"...
0x34a06  ldc.i4.3
0x34a07  newarr   [mscorlib]System.Object
0x34a0c  dup
0x34a0d  ldc.i4.0
0x34a0e  ldarg.1
0x34a0f  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x34a14  stelem.ref
0x34a15  dup
0x34a16  ldc.i4.1
0x34a17  ldloca.s 4
0x34a19  constrained. Microsoft.Crm.Asynchronous.EmailConnector.PromoteDecision
0x34a1f  callvirt instance string [mscorlib]System.Object::ToString()
0x34a24  stelem.ref
0x34a25  dup
0x34a26  ldc.i4.2
0x34a27  ldarg.0
0x34a28  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x34a2d  ldstr    aMailboxid// "mailboxid"
0x34a32  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x34a37  stelem.ref
0x34a38  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x34a3d  br       loc_34C5F
0x34a42  call     class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::get_Instance()
0x34a47  ldarg.1
0x34a48  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x34a4d  ldarg.0
0x34a4e  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x34a53  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x34a58  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailMessageIdCache::TryAddItem(string MessageID, valuetype [mscorlib]System.Guid OrganizationID)
0x34a5d  pop
0x34a5e  ldstr    aMailbox0Messag_0// "Mailbox: {0} - Message verification fai"...
0x34a63  ldarg.0
0x34a64  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x34a69  ldstr    aMailboxid// "mailboxid"
0x34a6e  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x34a73  ldarg.1
0x34a74  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x34a79  ldloca.s 4
0x34a7b  constrained. Microsoft.Crm.Asynchronous.EmailConnector.PromoteDecision
0x34a81  callvirt instance string [mscorlib]System.Object::ToString()
0x34a86  call     string [mscorlib]System.String::Format(string, object, object, object)
0x34a8b  stloc.s  0xD
0x34a8d  ldarg.0
0x34a8e  ldc.i4.3
0x34a8f  ldloc.s  0xD
0x34a91  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x34a96  ldarg.0
  ... truncated ...
```
