# Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::ProcessForwardMailbox

- ea: `0x3f050`
- end: `0x3f254`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::ProcessForwardMailbox`
- size: `516`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3dcb0`

## callees

- `0x32800`
- `0x32970`
- `0x32980`
- `0x329c0`
- `0x32a00`
- `0x32a20`
- `0x32a60`
- `0x3ab40`
- `0x3ae70`
- `0x3dbf0`
- `0x3f050`
- `0x3f260`
- `0x3f6a0`
- `0x40cc0`
- `0x41800`
- `0x41810`
- `0x41a20`
- `0x41b50`
- `0x41fb0`
- `0x41fd0`
- `0x41fe0`
- `0x42060`
- `0x4e480`
- `0x4e870`
- `0x4f250`
- `0x4f410`
- `0x516f0`
- `0x584c0`
- `0x71330`
- `0x71550`
- `0x71ff0`
- `0x814e0`
- `0x814f0`

## string_xrefs

- `0x3f1a7`: `Server-Side Synchronization (Incoming): Items Failed`
- `0x3f1b1`: `Server-Side Synchronization (Incoming): Items Failed Throughput`

## pseudocode

```c

```

## disassembly

```asm
0x3f050  ldarg.0
0x3f051  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3f056  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3f05b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_EmailMessages()
0x3f060  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage>::get_Count()
0x3f065  ldc.i4.1
0x3f066  sub
0x3f067  stloc.0
0x3f068  br       loc_3F24C
0x3f06d  ldarg.0
0x3f06e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3f073  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3f078  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_EmailMessages()
0x3f07d  ldloc.0
0x3f07e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage>::get_Item(!!T0)
0x3f083  castclass Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage
0x3f088  stloc.1
0x3f089  ldarg.0
0x3f08a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3f08f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3f094  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::set_DeliveredEmailCrmId(valuetype [mscorlib]System.Guid value)
0x3f099  ldarg.0
0x3f09a  ldloc.1
0x3f09b  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_From()
0x3f0a0  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::ParseEmail(string emailAddress)
0x3f0a5  stloc.2
0x3f0a6  ldarg.0
0x3f0a7  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3f0ac  ldarg.0
0x3f0ad  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3f0b2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3f0b7  ldstr    aMailboxid// "mailboxid"
0x3f0bc  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3f0c1  unbox.any [mscorlib]System.Guid
0x3f0c6  ldloc.1
0x3f0c7  ldarg.0
0x3f0c8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::syncResponseFactory
0x3f0cd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetEmptySyncResponse()
0x3f0d2  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context, valuetype [mscorlib]System.Guid mailboxId, class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage exchangeEmailMessage, class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse syncResponse)
0x3f0d7  stloc.3
0x3f0d8  ldloc.1
0x3f0d9  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::ValidateMessage()
0x3f0de  brfalse.s loc_3F0FB
0x3f0e0  ldarg.0
0x3f0e1  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3f0e6  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_ApprovedForwardMailboxUsersAndQueue()
0x3f0eb  ldloc.2
0x3f0ec  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x3f0f1  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x3f0f6  brtrue   loc_3F229
0x3f0fb  ldarg.0
0x3f0fc  ldc.i4.2
0x3f0fd  ldstr    aEmailForForwar_1// "Email  for Forward Mailbox {0} was reje"...
0x3f102  ldc.i4.1
0x3f103  newarr   [mscorlib]System.Object
0x3f108  dup
0x3f109  ldc.i4.0
0x3f10a  ldarg.0
0x3f10b  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3f110  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3f115  ldstr    aMailboxid// "mailboxid"
0x3f11a  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3f11f  stelem.ref
0x3f120  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3f125  ldarg.0
0x3f126  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3f12b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3f130  ldc.i4.s 0x1D
0x3f132  ldc.i4.2
0x3f133  ldc.i4.0
0x3f134  ldc.i4.0
0x3f135  ldc.i4.0
0x3f136  ldstr    aInvalidforward// "InvalidForwardMailItem"
0x3f13b  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x3f140  stloc.s  4
0x3f142  ldloc.s  4
0x3f144  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3f149  ldstr    aEmailForForwar_2// "Email for Forward Mailbox was rejected "...
0x3f14e  ldc.i4   0x400
0x3f153  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatExceptionMessage(string message, int32 maxLength)
0x3f158  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x3f15d  ldarg.0
0x3f15e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3f163  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3f168  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x3f16d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ErrorHandler()
0x3f172  ldloc.s  4
0x3f174  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler::HandleError(class Microsoft.Crm.Asynchronous.EmailConnector.IErrorInfo errorInfo)
0x3f179  ldloc.s  4
0x3f17b  ldloc.1
0x3f17c  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_Subject()
0x3f181  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x3f186  ldc.i4.0
0x3f187  call     void Microsoft.Crm.Asynchronous.EmailConnector.TraceLogHelper::InsertTextTypeTraceParameter(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo errorInfo, string data, int32 index)
0x3f18c  ldarg.0
0x3f18d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3f192  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3f197  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_FailedEmails()
0x3f19c  ldloc.1
0x3f19d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x3f1a2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType>::Add(var<u1>)
0x3f1a7  ldstr    aServerSideSync_8// "Server-Side Synchronization (Incoming):"...
0x3f1ac  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x3f1b1  ldstr    aServerSideSync_9// "Server-Side Synchronization (Incoming):"...
0x3f1b6  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x3f1bb  ldloc.3
0x3f1bc  ldarg.0
0x3f1bd  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::syncResponseFactory
0x3f1c2  ldloc.s  4
0x3f1c4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3f1c9  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.TraceData::get_TraceCode()
0x3f1ce  ldloc.s  4
0x3f1d0  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3f1d5  callvirt instance string [Microsoft.Crm]Microsoft.Crm.TraceData::get_ErrorDetails()
0x3f1da  ldc.i4.0
0x3f1db  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetErrorSyncResponse(int32 traceCode, string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeType)
0x3f1e0  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x3f1e5  ldarg.0
0x3f1e6  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::EmailMessageUpdateRequired()
0x3f1eb  brfalse.s loc_3F213
0x3f1ed  ldarg.0
0x3f1ee  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3f1f3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3f1f8  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_EmailMessageUpdates()
0x3f1fd  ldloc.1
0x3f1fe  ldarg.0
0x3f1ff  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3f204  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_DeliveredEmailCrmId()
0x3f209  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage emailMessage, valuetype [mscorlib]System.Guid crmId)
0x3f20e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage>::Add(var<u1>)
0x3f213  ldarg.0
0x3f214  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3f219  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3f21e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_EmailMessages()
0x3f223  ldloc.0
0x3f224  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage>::RemoveAt(int32)
0x3f229  ldarg.0
0x3f22a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3f22f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3f234  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_IsSynchronousEwsFcbEnabled()
0x3f239  brfalse.s loc_3F241
0x3f23b  ldarg.0
0x3f23c  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::ProcessAttachmentsForSynchronousEws()
0x3f241  ldarg.0
0x3f242  ldloc.3
0x3f243  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::LogIncomingItemStatistics(class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats incomingEmailStats)
0x3f248  ldloc.0
0x3f249  ldc.i4.1
0x3f24a  sub
0x3f24b  stloc.0
0x3f24c  ldloc.0
0x3f24d  ldc.i4.0
0x3f24e  bge      loc_3F06D
0x3f253  ret
```
