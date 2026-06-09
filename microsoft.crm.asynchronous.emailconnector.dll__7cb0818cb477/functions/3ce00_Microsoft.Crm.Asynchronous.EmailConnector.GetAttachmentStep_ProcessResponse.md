# Microsoft.Crm.Asynchronous.EmailConnector.GetAttachmentStep::ProcessResponse

- ea: `0x3ce00`
- end: `0x3d4fa`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.GetAttachmentStep::ProcessResponse`
- size: `1786`
- prototype: ``
- caller_count: `0`
- callee_count: `66`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x13fd0`
- `0x13ff0`
- `0x14070`
- `0x14090`
- `0x181e0`
- `0x18260`
- `0x18c40`
- `0x18d70`
- `0x18de0`
- `0x18e00`
- `0x18e20`
- `0x18f40`
- `0x24290`
- `0x25060`
- `0x25110`
- `0x32800`
- `0x32970`
- `0x32980`
- `0x329c0`
- `0x32a00`
- `0x32a20`
- `0x32a60`
- `0x3a170`
- `0x3ab40`
- `0x3ab80`
- `0x3ac40`
- `0x3ae70`
- `0x3cde0`
- `0x3ce00`
- `0x3d500`
- `0x3d790`
- `0x40cc0`
- `0x40d80`
- `0x417a0`
- `0x41800`
- `0x41850`
- `0x41980`
- `0x41990`
- `0x419a0`
- `0x419b0`
- `0x419c0`
- `0x419d0`
- `0x419e0`
- `0x419f0`
- `0x41a20`
- `0x41b80`
- `0x41ba0`
- `0x41bd0`
- `0x41fd0`
- `0x41fe0`

## string_xrefs

- `0x3cfbf`: `Server-Side Synchronization (Incoming): Items Suspected`
- `0x3d28d`: `Server-Side Synchronization (Incoming): Items Suspected`
- `0x3cfc9`: `Server-Side Synchronization (Incoming): Items Suspected Throughput`
- `0x3d297`: `Server-Side Synchronization (Incoming): Items Suspected Throughput`
- `0x3d03f`: `Server-Side Synchronization (Incoming): Items Failed`
- `0x3d3d5`: `Server-Side Synchronization (Incoming): Items Failed`
- `0x3d049`: `Server-Side Synchronization (Incoming): Items Failed Throughput`
- `0x3d3df`: `Server-Side Synchronization (Incoming): Items Failed Throughput`

## pseudocode

```c

```

## disassembly

```asm
0x3ce00  ldarg.0
0x3ce01  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3ce06  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3ce0b  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_EmailMessages()
0x3ce10  call     T0x2B000075
0x3ce15  brfalse  loc_3D49E
0x3ce1a  ldarg.0
0x3ce1b  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3ce20  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3ce25  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_EmailMessages()
0x3ce2a  ldc.i4.0
0x3ce2b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage>::get_Item(!!T0)
0x3ce30  castclass Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage
0x3ce35  stloc.0
0x3ce36  ldloc.0
0x3ce37  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_EmbeddedMessage()
0x3ce3c  brtrue.s loc_3CE41
0x3ce3e  ldloc.0
0x3ce3f  br.s     loc_3CE47
0x3ce41  ldloc.0
0x3ce42  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_EmbeddedMessage()
0x3ce47  stloc.0
0x3ce48  ldarg.0
0x3ce49  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3ce4e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3ce53  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::set_DeliveredEmailCrmId(valuetype [mscorlib]System.Guid value)
0x3ce58  ldloc.0
0x3ce59  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_IsForwardMailboxEmail()
0x3ce5e  stloc.1
0x3ce5f  ldarg.0
0x3ce60  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3ce65  ldarg.0
0x3ce66  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3ce6b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3ce70  ldstr    aMailboxid// "mailboxid"
0x3ce75  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3ce7a  unbox.any [mscorlib]System.Guid
0x3ce7f  ldloc.0
0x3ce80  ldarg.0
0x3ce81  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::syncResponseFactory
0x3ce86  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetEmptySyncResponse()
0x3ce8b  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context, valuetype [mscorlib]System.Guid mailboxId, class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage exchangeEmailMessage, class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse syncResponse)
0x3ce90  stloc.2
0x3ce91  ldarg.0
0x3ce92  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::IsInvalidResponse()
0x3ce97  brfalse.s loc_3CF01
0x3ce99  ldarg.0
0x3ce9a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3ce9f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3cea4  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_EmailMessages()
0x3cea9  ldc.i4.0
0x3ceaa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage>::RemoveAt(int32)
0x3ceaf  ldarg.0
0x3ceb0  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3ceb5  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::CheckForMailboxProcessed()
0x3ceba  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3cebf  ldstr    aInvalidRespons// "Invalid response while fetching email-a"...
0x3cec4  ldc.i4.1
0x3cec5  newarr   [mscorlib]System.Object
0x3ceca  dup
0x3cecb  ldc.i4.0
0x3cecc  ldloc.0
0x3cecd  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_MessageId()
0x3ced2  stelem.ref
0x3ced3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3ced8  stloc.s  5
0x3ceda  ldarg.0
0x3cedb  ldc.i4.1
0x3cedc  ldloc.s  5
0x3cede  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x3cee3  ldloc.2
0x3cee4  ldarg.0
0x3cee5  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::syncResponseFactory
0x3ceea  ldc.i4.0
0x3ceeb  ldloc.s  5
0x3ceed  ldc.i4.1
0x3ceee  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetErrorSyncResponse(int32 traceCode, string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeType)
0x3cef3  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x3cef8  ldarg.0
0x3cef9  ldloc.2
0x3cefa  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::LogIncomingItemStatistics(class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats incomingEmailStats)
0x3ceff  ldc.i4.1
0x3cf00  ret
0x3cf01  ldarg.0
0x3cf02  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.GetAttachmentResponseType Microsoft.Crm.Asynchronous.EmailConnector.GetAttachmentStep::response
0x3cf07  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x3cf0c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x3cf11  ldc.i4.0
0x3cf12  ldelem.ref
0x3cf13  stloc.3
0x3cf14  ldloc.3
0x3cf15  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ResponseClassType Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_ResponseClass()
0x3cf1a  brfalse  loc_3D0C1
0x3cf1f  ldloc.3
0x3cf20  call     T0x2B000070
0x3cf25  stloc.s  6
0x3cf27  ldarg.0
0x3cf28  ldc.i4.1
0x3cf29  ldstr    aFailureFoundWh// "Failure found while fetching email-atta"...
0x3cf2e  ldc.i4.1
0x3cf2f  newarr   [mscorlib]System.Object
0x3cf34  dup
0x3cf35  ldc.i4.0
0x3cf36  ldloc.s  6
0x3cf38  stelem.ref
0x3cf39  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3cf3e  call     class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeErrorCodeProcessor Microsoft.Crm.Asynchronous.EmailConnector.ExchangeErrorCodeProcessor::get_Instance()
0x3cf43  ldloc.3
0x3cf44  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ResponseCodeType Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_ResponseCode()
0x3cf49  ldloc.3
0x3cf4a  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_MessageText()
0x3cf4f  ldc.i4.0
0x3cf50  ldloc.3
0x3cf51  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageTypeMessageXml Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_MessageXml()
0x3cf56  ldarg.0
0x3cf57  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3cf5c  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_DefaultErrorType()
0x3cf61  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeErrorCodeProcessor::GetErrorInfo(int32 errorCode, string responseMessage, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageTypeMessageXml responseMessageXml, [opt] valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType)
0x3cf66  stloc.s  7
0x3cf68  ldloc.s  7
0x3cf6a  brfalse  loc_3D06F
0x3cf6f  ldloc.s  7
0x3cf71  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3cf76  brfalse.s loc_3CF8B
0x3cf78  ldloc.s  7
0x3cf7a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3cf7f  ldloc.s  6
0x3cf81  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatTraceLogErrorDetail(string message)
0x3cf86  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x3cf8b  ldloc.s  7
0x3cf8d  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo::get_ErrorScope()
0x3cf92  brtrue.s loc_3CF9C
0x3cf94  ldloc.s  7
0x3cf96  ldc.i4.1
0x3cf97  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo::set_ErrorScope(valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope value)
0x3cf9c  ldloc.s  7
0x3cf9e  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo::get_ErrorScope()
0x3cfa3  ldc.i4.1
0x3cfa4  bne.un   loc_3D053
0x3cfa9  ldloc.s  7
0x3cfab  ldloc.0
0x3cfac  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage::get_Subject()
0x3cfb1  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x3cfb6  ldc.i4.0
0x3cfb7  call     void Microsoft.Crm.Asynchronous.EmailConnector.TraceLogHelper::InsertTextTypeTraceParameter(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo errorInfo, string data, int32 index)
0x3cfbc  ldloc.1
0x3cfbd  brfalse.s loc_3CFD3
0x3cfbf  ldstr    aServerSideSync_4// "Server-Side Synchronization (Incoming):"...
0x3cfc4  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x3cfc9  ldstr    aServerSideSync_5// "Server-Side Synchronization (Incoming):"...
0x3cfce  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x3cfd3  ldarg.0
0x3cfd4  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3cfd9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3cfde  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_FailedEmails()
0x3cfe3  ldarg.0
0x3cfe4  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3cfe9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3cfee  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_EmailMessages()
0x3cff3  ldc.i4.0
0x3cff4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage>::get_Item(!!T0)
0x3cff9  castclass Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage
0x3cffe  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x3d003  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType>::Contains(var<u1>)
0x3d008  brtrue.s loc_3D053
0x3d00a  ldarg.0
0x3d00b  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3d010  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3d015  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_FailedEmails()
0x3d01a  ldarg.0
0x3d01b  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3d020  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3d025  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_EmailMessages()
0x3d02a  ldc.i4.0
0x3d02b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailMessage>::get_Item(!!T0)
0x3d030  castclass Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage
0x3d035  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x3d03a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType>::Add(var<u1>)
0x3d03f  ldstr    aServerSideSync_8// "Server-Side Synchronization (Incoming):"...
0x3d044  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x3d049  ldstr    aServerSideSync_9// "Server-Side Synchronization (Incoming):"...
0x3d04e  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x3d053  ldarg.0
0x3d054  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3d059  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3d05e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x3d063  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ErrorHandler()
0x3d068  ldloc.s  7
0x3d06a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler::HandleError(class Microsoft.Crm.Asynchronous.EmailConnector.IErrorInfo errorInfo)
0x3d06f  ldloc.2
0x3d070  ldarg.0
0x3d071  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::syncResponseFactory
0x3d076  ldloc.s  7
0x3d078  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3d07d  brtrue.s loc_3D082
0x3d07f  ldc.i4.2
0x3d080  br.s     loc_3D08E
0x3d082  ldloc.s  7
0x3d084  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3d089  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.TraceData::get_TraceCode()
0x3d08e  ldloc.s  7
0x3d090  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3d095  brtrue.s loc_3D09E
0x3d097  ldsfld   string [mscorlib]System.String::Empty
0x3d09c  br.s     loc_3D0AA
0x3d09e  ldloc.s  7
0x3d0a0  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3d0a5  callvirt instance string [Microsoft.Crm]Microsoft.Crm.TraceData::get_ErrorDetails()
0x3d0aa  ldc.i4.1
0x3d0ab  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.ISyncResponseFactory::GetErrorSyncResponse(int32 traceCode, string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeType)
0x3d0b0  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x3d0b5  ldarg.0
0x3d0b6  ldloc.2
0x3d0b7  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::LogIncomingItemStatistics(class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailStats incomingEmailStats)
0x3d0bc  br       loc_3D454
0x3d0c1  ldloc.0
0x3d0c2  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.AttachmentType> Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_AttachmentTypes()
0x3d0c7  ldloc.0
0x3d0c8  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_RetrieveAttachmentIndex()
0x3d0cd  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Asynchronous.EmailConnector.AttachmentType>::get_Item(!!T0)
0x3d0d2  dup
0x3d0d3  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.AttachmentType::get_Name()
0x3d0d8  stloc.s  8
0x3d0da  dup
0x3d0db  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.AttachmentType::get_ContentType()
0x3d0e0  stloc.s  9
0x3d0e2  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.AttachmentType::get_ContentId()
0x3d0e7  stloc.s  0xA
0x3d0e9  ldloc.3
0x3d0ea  isinst   Microsoft.Crm.Asynchronous.EmailConnector.AttachmentInfoResponseMessageType
0x3d0ef  stloc.s  0xB
0x3d0f1  ldstr    aActivitymimeat// "activitymimeattachment"
0x3d0f6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x3d0fb  stloc.s  0xC
0x3d0fd  ldloc.s  0xB
0x3d0ff  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.AttachmentType[] Microsoft.Crm.Asynchronous.EmailConnector.AttachmentInfoResponseMessageType::get_Attachments()
0x3d104  ldc.i4.0
0x3d105  ldelem.ref
0x3d106  isinst   Microsoft.Crm.Asynchronous.EmailConnector.FileAttachmentType
0x3d10b  stloc.s  0xD
0x3d10d  ldnull
0x3d10e  stloc.s  0xE
0x3d110  ldloc.s  0xD
0x3d112  brfalse  loc_3D198
0x3d117  ldloc.s  0xD
0x3d119  callvirt instance unsigned int8[] Microsoft.Crm.Asynchronous.EmailConnector.FileAttachmentType::get_Content()
0x3d11e  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x3d123  stloc.s  0xF
0x3d125  ldloc.s  9
0x3d127  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3d12c  brfalse.s loc_3D135
0x3d12e  ldstr    aApplicationOct// "application/octet-stream"
0x3d133  stloc.s  9
0x3d135  ldloc.s  0xA
0x3d137  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3d13c  brtrue.s loc_3D164
0x3d13e  ldloc.s  0xC
0x3d140  ldstr    aAttachmentcont// "attachmentcontentid"
0x3d145  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3d14a  ldstr    aCid0// "{{cid:{0}}}"
0x3d14f  ldc.i4.1
0x3d150  newarr   [mscorlib]System.Object
0x3d155  dup
0x3d156  ldc.i4.0
0x3d157  ldloc.s  0xA
0x3d159  stelem.ref
0x3d15a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3d15f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x3d164  ldloc.s  0xC
0x3d166  ldstr    aBody// "body"
0x3d16b  ldloc.s  0xF
0x3d16d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x3d172  ldloc.s  0xC
0x3d174  ldstr    aFilename// "filename"
0x3d179  ldloc.s  8
0x3d17b  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::NormalizeAttachmentFileName(string fileName)
0x3d180  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x3d185  ldloc.s  0xC
0x3d187  ldstr    aMimetype// "mimetype"
0x3d18c  ldloc.s  9
0x3d18e  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x3d193  br       loc_3D24F
0x3d198  ldloc.s  0xB
0x3d19a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.AttachmentType[] Microsoft.Crm.Asynchronous.EmailConnector.AttachmentInfoResponseMessageType::get_Attachments()
0x3d19f  ldc.i4.0
0x3d1a0  ldelem.ref
0x3d1a1  isinst   Microsoft.Crm.Asynchronous.EmailConnector.ItemAttachmentType
0x3d1a6  stloc.s  0xE
0x3d1a8  ldloc.s  0xE
0x3d1aa  brfalse  loc_3D24F
0x3d1af  ldloc.1
0x3d1b0  brtrue   loc_3D24F
0x3d1b5  ldloc.s  0xE
0x3d1b7  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemType Microsoft.Crm.Asynchronous.EmailConnector.ItemAttachmentType::get_Item()
0x3d1bc  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MimeContentType Microsoft.Crm.Asynchronous.EmailConnector.ItemType::get_MimeContent()
0x3d1c1  brtrue.s loc_3D1CA
0x3d1c3  ldsfld   string [mscorlib]System.String::Empty
0x3d1c8  br.s     loc_3D1DB
0x3d1ca  ldloc.s  0xE
0x3d1cc  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemType Microsoft.Crm.Asynchronous.EmailConnector.ItemAttachmentType::get_Item()
  ... truncated ...
```
