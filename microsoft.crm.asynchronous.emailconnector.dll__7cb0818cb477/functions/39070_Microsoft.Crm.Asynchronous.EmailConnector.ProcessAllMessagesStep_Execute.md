# Microsoft.Crm.Asynchronous.EmailConnector.ProcessAllMessagesStep::Execute

- ea: `0x39070`
- end: `0x394d9`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ProcessAllMessagesStep::Execute`
- size: `1129`
- prototype: ``
- caller_count: `0`
- callee_count: `44`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x30850`
- `0x30990`
- `0x309b0`
- `0x309f0`
- `0x32960`
- `0x32970`
- `0x32980`
- `0x34c70`
- `0x35770`
- `0x35790`
- `0x357e0`
- `0x357f0`
- `0x35820`
- `0x35840`
- `0x35c10`
- `0x362c0`
- `0x36b40`
- `0x36b50`
- `0x36b70`
- `0x36b90`
- `0x36ba0`
- `0x36be0`
- `0x37030`
- `0x37060`
- `0x37140`
- `0x388b0`
- `0x38af0`
- `0x39040`
- `0x39070`
- `0x394e0`
- `0x41920`
- `0x4e480`
- `0x4e870`
- `0x4f410`
- `0x517c0`
- `0x71400`
- `0x71540`
- `0x71550`
- `0x71ff0`
- `0x7aa20`
- `0x814e0`
- `0x81500`
- `0x81590`
- `0x81640`

## string_xrefs

- `0x39367`: `processanddeleteemails`
- `0x39211`: `Server-Side Synchronization (Incoming): Items Discarded`
- `0x3921b`: `Server-Side Synchronization (Incoming): Items Discarded Throughput`
- `0x390ee`: `Server-Side Synchronization (Incoming): Items Failed`
- `0x393ff`: `Server-Side Synchronization (Incoming): Items Failed`
- `0x390f8`: `Server-Side Synchronization (Incoming): Items Failed Throughput`
- `0x39409`: `Server-Side Synchronization (Incoming): Items Failed Throughput`
- `0x390ca`: `Server-Side Synchronization (Incoming): Emails Processed`
- `0x390d4`: `Server-Side Synchronization (Incoming): Items Processed Throughput`

## pseudocode

```c

```

## disassembly

```asm
0x39070  ldc.i4.1
0x39071  stloc.0
0x39072  ldc.i4.2
0x39073  ldarg.0
0x39074  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x39079  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ConnectionState Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider::get_ConnectionState()
0x3907e  ceq
0x39080  ldstr    aConnectstateSh_0// "ConnectState should be Transaction"
0x39085  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x3908a  br       loc_394C6
0x3908f  ldarg.0
0x39090  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep> Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::childStepsList
0x39095  ldc.i4.0
0x39096  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep>::get_Item(!!T0)
0x3909b  stloc.1
0x3909c  ldloc.1
0x3909d  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::Execute()
0x390a2  stloc.0
0x390a3  ldloc.0
0x390a4  ldc.i4.1
0x390a5  beq.s    loc_390A9
0x390a7  ldloc.0
0x390a8  ret
0x390a9  ldarg.0
0x390aa  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x390af  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider::get_ProviderContext()
0x390b4  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext::get_IsInTestAccessContext()
0x390b9  brfalse.s loc_390BD
0x390bb  ldc.i4.1
0x390bc  ret
0x390bd  ldloc.1
0x390be  isinst   Microsoft.Crm.Asynchronous.EmailConnector.DownloadMessageStep
0x390c3  stloc.2
0x390c4  ldloc.2
0x390c5  brfalse  loc_394BA
0x390ca  ldstr    aServerSideSync_12// "Server-Side Synchronization (Incoming):"...
0x390cf  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x390d4  ldstr    aServerSideSync_13// "Server-Side Synchronization (Incoming):"...
0x390d9  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x390de  ldarg.0
0x390df  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x390e4  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_ErrorResponseReturned()
0x390e9  brfalse  loc_3916F
0x390ee  ldstr    aServerSideSync_8// "Server-Side Synchronization (Incoming):"...
0x390f3  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x390f8  ldstr    aServerSideSync_9// "Server-Side Synchronization (Incoming):"...
0x390fd  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x39102  ldarg.0
0x39103  ldc.i4.2
0x39104  ldstr    aErrorOccurredI_1// "Error Occurred in Downloading Email for"...
0x39109  ldc.i4.1
0x3910a  newarr   [mscorlib]System.Object
0x3910f  dup
0x39110  ldc.i4.0
0x39111  ldarg.0
0x39112  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x39117  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x3911c  ldstr    aMailboxid// "mailboxid"
0x39121  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x39126  stelem.ref
0x39127  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3912c  ldc.i4.s 0x1B
0x3912e  ldc.i4.1
0x3912f  ldc.i4.s 9
0x39131  ldc.i4.4
0x39132  ldc.i4.0
0x39133  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo::.ctor(int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType operationType)
0x39138  stloc.s  9
0x3913a  ldloc.s  9
0x3913c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x39141  ldarg.0
0x39142  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x39147  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_ExchangeErrorResponse()
0x3914c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x39151  ldarg.0
0x39152  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x39157  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x3915c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x39161  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ErrorHandler()
0x39166  ldloc.s  9
0x39168  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler::HandleError(class Microsoft.Crm.Asynchronous.EmailConnector.IErrorInfo errorInfo)
0x3916d  ldc.i4.3
0x3916e  ret
0x3916f  ldloc.2
0x39170  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.DownloadMessageStep::EmailMessage
0x39175  castclass Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage
0x3917a  stloc.3
0x3917b  ldarg.0
0x3917c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x39181  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider::get_ProviderContext()
0x39186  ldarg.0
0x39187  ldarg.0
0x39188  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x3918d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x39192  ldstr    aMailboxid// "mailboxid"
0x39197  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3919c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ProcessAllMessagesStep::GetMailboxId(object id)
0x391a1  ldloc.3
0x391a2  ldarg.0
0x391a3  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.ProcessAllMessagesStep::syncResponseFactory
0x391a8  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetEmptySyncResponse()
0x391ad  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context, valuetype [mscorlib]System.Guid mailboxId, class Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage pop3EmailMessage, class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse syncResponse)
0x391b2  stloc.s  4
0x391b4  ldc.i4.0
0x391b5  stloc.s  5
0x391b7  ldloc.3
0x391b8  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::get_From()
0x391bd  ldc.i4.0
0x391be  ldc.i4.0
0x391bf  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.EmailAddressData> [Microsoft.Crm]Microsoft.Crm.EmailAddressParser::Parse(string, bool, bool)
0x391c4  stloc.s  6
0x391c6  ldsfld   string [mscorlib]System.String::Empty
0x391cb  stloc.s  7
0x391cd  ldloc.s  6
0x391cf  brfalse.s loc_391EA
0x391d1  ldloc.s  6
0x391d3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.EmailAddressData>::get_Count()
0x391d8  ldc.i4.0
0x391d9  ble.s    loc_391EA
0x391db  ldloc.s  6
0x391dd  ldc.i4.0
0x391de  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.EmailAddressData>::get_Item(!!T0)
0x391e3  callvirt instance string [Microsoft.Crm]Microsoft.Crm.EmailAddressData::get_EmailAddress()
0x391e8  stloc.s  7
0x391ea  ldloc.3
0x391eb  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::get_MessageId()
0x391f0  ldarg.0
0x391f1  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x391f6  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x391fb  ldstr    aLastmessageid// "lastmessageid"
0x39200  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x39205  castclass [mscorlib]System.String
0x3920a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3920f  brfalse.s loc_3922A
0x39211  ldstr    aServerSideSync_6// "Server-Side Synchronization (Incoming):"...
0x39216  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x3921b  ldstr    aServerSideSync_7// "Server-Side Synchronization (Incoming):"...
0x39220  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x39225  br       loc_392FF
0x3922a  ldarg.0
0x3922b  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x39230  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x39235  ldstr    aIsforwardmailb// "isforwardmailbox"
0x3923a  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3923f  unbox.any [mscorlib]System.Boolean
0x39244  brfalse.s loc_39262
0x39246  ldarg.0
0x39247  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x3924c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_ApprovedForwardMailboxUsersAndQueue()
0x39251  ldloc.s  7
0x39253  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x39258  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x3925d  brfalse  loc_392E5
0x39262  ldloc.3
0x39263  ldarg.0
0x39264  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x39269  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x3926e  ldstr    aIsforwardmailb// "isforwardmailbox"
0x39273  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x39278  unbox.any [mscorlib]System.Boolean
0x3927d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::ValidateMessage(bool isForwardMailbox)
0x39282  stloc.s  8
0x39284  ldloc.s  8
0x39286  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncStatus Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse::get_SyncStatus()
0x3928b  brtrue.s loc_392D2
0x3928d  ldarg.0
0x3928e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x39293  ldloc.3
0x39294  ldc.i4.1
0x39295  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::DeliverMessage(class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage emailMessage, bool validateBeforeCreate)
0x3929a  ldarg.0
0x3929b  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x392a0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_DeliveredEmailCrmId()
0x392a5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x392aa  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x392af  brfalse.s loc_392B6
0x392b1  ldc.i4.1
0x392b2  stloc.s  5
0x392b4  br.s     loc_392FF
0x392b6  ldloc.s  4
0x392b8  ldarg.0
0x392b9  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x392be  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_SyncResponse()
0x392c3  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x392c8  ldarg.0
0x392c9  ldloc.s  4
0x392cb  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ProcessAllMessagesStep::LogIncomingItemStatistics(class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats incomingEmailStats)
0x392d0  br.s     loc_392FF
0x392d2  ldloc.s  4
0x392d4  ldloc.s  8
0x392d6  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x392db  ldarg.0
0x392dc  ldloc.s  4
0x392de  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ProcessAllMessagesStep::LogIncomingItemStatistics(class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats incomingEmailStats)
0x392e3  br.s     loc_392FF
0x392e5  ldloc.s  4
0x392e7  ldarg.0
0x392e8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x392ed  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_SyncResponse()
0x392f2  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x392f7  ldarg.0
0x392f8  ldloc.s  4
0x392fa  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ProcessAllMessagesStep::LogIncomingItemStatistics(class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats incomingEmailStats)
0x392ff  ldarg.0
0x39300  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x39305  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x3930a  ldstr    aProcessemailre// "processemailreceivedafter"
0x3930f  ldloc.3
0x39310  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::get_TimeReceived()
0x39315  box      [mscorlib]System.DateTime
0x3931a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::set_Item(string attributeName, object value)
0x3931f  ldarg.0
0x39320  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x39325  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x3932a  ldstr    aLastmessageid// "lastmessageid"
0x3932f  ldloc.3
0x39330  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::get_MessageId()
0x39335  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::set_Item(string attributeName, object value)
0x3933a  ldloc.s  5
0x3933c  brfalse  loc_393FF
0x39341  ldarg.0
0x39342  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x39347  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x3934c  ldstr    aNoemailcount// "noemailcount"
0x39351  ldc.i4.0
0x39352  box      [mscorlib]System.Int32
0x39357  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::set_Item(string attributeName, object value)
0x3935c  ldarg.0
0x3935d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x39362  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x39367  ldstr    aProcessanddele// "processanddeleteemails"
0x3936c  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x39371  unbox.any [mscorlib]System.Boolean
0x39376  brfalse.s loc_39399
0x39378  ldarg.0
0x39379  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep> Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::childStepsList
0x3937e  ldarg.0
0x3937f  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x39384  ldarg.0
0x39385  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x3938a  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider::get_MessagePosition()
0x3938f  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.DeleteMessageStep::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider provider, int32 messagePosition)
0x39394  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep>::Add(var<u1>)
0x39399  ldarg.0
0x3939a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x3939f  ldc.i4.1
0x393a0  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::set_IsSingleEmailDeliveredToCrm(bool value)
0x393a5  ldloc.s  4
0x393a7  ldarg.0
0x393a8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.ProcessAllMessagesStep::syncResponseFactory
0x393ad  ldstr    aThePop3EmailIs// "The POP3 Email is delivered to CRM succ"...
0x393b2  ldc.i4.1
0x393b3  ldc.i4.0
0x393b4  ldstr    asc_8A7C2// ""
0x393b9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetSuccessSyncResponse(string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeTypeInCrm, [opt] int32 traceCode, [opt] string traceCodeString)
0x393be  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x393c3  ldloc.s  4
0x393c5  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats::get_SyncResponse()
0x393ca  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x393cf  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse::set_TimeSyncedInCrm(valuetype [mscorlib]System.DateTime value)
0x393d4  ldloc.s  4
0x393d6  ldarg.0
0x393d7  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x393dc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_DeliveredEmailCrmId()
0x393e1  stloc.s  0xA
0x393e3  ldloca.s 0xA
0x393e5  constrained. [mscorlib]System.Guid
0x393eb  callvirt instance string [mscorlib]System.Object::ToString()
0x393f0  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.ItemStatsBase::set_CrmId(string value)
0x393f5  ldarg.0
0x393f6  ldloc.s  4
0x393f8  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ProcessAllMessagesStep::LogIncomingItemStatistics(class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats incomingEmailStats)
0x393fd  br.s     loc_39446
0x393ff  ldstr    aServerSideSync_8// "Server-Side Synchronization (Incoming):"...
0x39404  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x39409  ldstr    aServerSideSync_9// "Server-Side Synchronization (Incoming):"...
0x3940e  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x39413  ldarg.0
0x39414  ldc.i4.4
0x39415  ldstr    aMessageWithId0// "Message with Id: {0} wasn't accepted by"...
0x3941a  ldc.i4.2
0x3941b  newarr   [mscorlib]System.Object
0x39420  dup
0x39421  ldc.i4.0
0x39422  ldloc.3
0x39423  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::get_MessageId()
0x39428  stelem.ref
0x39429  dup
0x3942a  ldc.i4.1
0x3942b  ldarg.0
0x3942c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x39431  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x39436  ldstr    aMailboxid// "mailboxid"
0x3943b  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x39440  stelem.ref
0x39441  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x39446  ldarg.0
0x39447  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x3944c  dup
0x3944d  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider::get_MessagePosition()
  ... truncated ...
```
