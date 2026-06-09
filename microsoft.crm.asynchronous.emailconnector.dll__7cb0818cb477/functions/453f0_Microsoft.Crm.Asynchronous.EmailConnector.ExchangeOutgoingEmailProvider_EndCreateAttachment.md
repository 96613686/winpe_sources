# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::EndCreateAttachment

- ea: `0x453f0`
- end: `0x4581c`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::EndCreateAttachment`
- size: `1068`
- prototype: ``
- caller_count: `2`
- callee_count: `48`
- tags: `broker_com_uri`

## callers

- `0x43920`
- `0x45280`

## callees

- `0xb9b0`
- `0x10150`
- `0x13fd0`
- `0x13ff0`
- `0x14070`
- `0x14090`
- `0x14520`
- `0x14710`
- `0x18dc0`
- `0x24290`
- `0x25060`
- `0x25110`
- `0x417a0`
- `0x420e0`
- `0x42170`
- `0x43600`
- `0x43660`
- `0x43680`
- `0x43690`
- `0x436d0`
- `0x43710`
- `0x43780`
- `0x437c0`
- `0x437d0`
- `0x43880`
- `0x44ce0`
- `0x45280`
- `0x453f0`
- `0x46320`
- `0x463f0`
- `0x46d70`
- `0x46e60`
- `0x47110`
- `0x47b50`
- `0x47c00`
- `0x4da80`
- `0x4f410`
- `0x501e0`
- `0x50b40`
- `0x50ea0`
- `0x516f0`
- `0x51950`
- `0x51960`
- `0x58580`
- `0x7aad0`
- `0x7ad00`
- `0x81680`
- `0x816a0`

## string_xrefs

- `0x4549c`: `CreateAttachment`
- `0x45420`: `Ending create attachement for outgoing activity {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x453f0  ldarg.0
0x453f1  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_ExchangeOutgoingEmailsWorkingSet()
0x453f6  ldc.i4.0
0x453f7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::get_Item(!!T0)
0x453fc  stloc.0
0x453fd  ldloc.0
0x453fe  ldarg.0
0x453ff  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::syncResponseFactory
0x45404  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponseFactory::GetEmptySyncResponse()
0x45409  ldarg.0
0x4540a  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x4540f  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.OutgoingEmailStats::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail exchangeOutgoingEmail, class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse syncResponse, class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context)
0x45414  stloc.1
0x45415  ldarg.0
0x45416  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.CreateAttachmentResponseType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_CreateAttachmentResponse()
0x4541b  stloc.2
0x4541c  ldnull
0x4541d  stloc.3
0x4541e  ldarg.0
0x4541f  ldc.i4.3
0x45420  ldstr    aEndingCreateAt// "Ending create attachement for outgoing "...
0x45425  ldc.i4.1
0x45426  newarr   [mscorlib]System.Object
0x4542b  dup
0x4542c  ldc.i4.0
0x4542d  ldloc.0
0x4542e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x45433  brfalse.s loc_45442
0x45435  ldloc.0
0x45436  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x4543b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x45440  brtrue.s loc_45449
0x45442  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x45447  br.s     loc_45459
0x45449  ldloc.0
0x4544a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x4544f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x45454  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x45459  box      [mscorlib]System.Guid
0x4545e  stelem.ref
0x4545f  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::HandleTraceForOutgoingActivityProvider(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x45464  ldarg.0
0x45465  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::get_IsSynchronousEwsFcbEnabled()
0x4546a  brtrue   loc_4554C
0x4546f  ldc.i4.3
0x45470  ldarg.0
0x45471  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x45476  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x4547b  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventExecutionStatus [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_Status()
0x45480  bne.un.s loc_45488
0x45482  ldarg.0
0x45483  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::AbortCurrentRequest()
0x45488  nop
0x45489  ldarg.0
0x4548a  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeServiceBinding Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_ExchangeServiceBinding()
0x4548f  ldarg.0
0x45490  call     instance class [mscorlib]System.IAsyncResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_CreateAttachmentAsyncResult()
0x45495  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.CreateAttachmentResponseType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeServiceBinding::EndCreateAttachment(class [mscorlib]System.IAsyncResult asyncResult)
0x4549a  stloc.2
0x4549b  ldarg.0
0x4549c  ldstr    aCreateattachme// "CreateAttachment"
0x454a1  ldarg.0
0x454a2  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::createAttachmentStopwatch
0x454a7  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::ReportStepTiming(string stepName, class [System]System.Diagnostics.Stopwatch stopwatch)
0x454ac  leave    loc_4554C
0x454b1  stloc.s  4
0x454b3  ldstr    aErrorCreatingA_0// "Error creating attachment(s) for outgoi"...
0x454b8  ldloc.0
0x454b9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x454be  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x454c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x454c8  box      [mscorlib]System.Guid
0x454cd  ldloc.s  4
0x454cf  ldarg.0
0x454d0  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x454d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x454da  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x454df  call     string [mscorlib]System.String::Format(string, object, object)
0x454e4  stloc.s  5
0x454e6  ldarg.0
0x454e7  ldc.i4.1
0x454e8  ldloc.s  5
0x454ea  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x454ef  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x454f4  ldarg.0
0x454f5  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x454fa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x454ff  ldloc.s  4
0x45501  ldc.i4.1
0x45502  ldc.i4.1
0x45503  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x45508  stloc.3
0x45509  ldloc.3
0x4550a  brfalse.s loc_4552B
0x4550c  ldloc.3
0x4550d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x45512  brfalse.s loc_4552B
0x45514  ldloc.3
0x45515  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x4551a  ldloc.s  4
0x4551c  callvirt instance string [mscorlib]System.Object::ToString()
0x45521  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatTraceLogErrorDetail(string message)
0x45526  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x4552b  ldloc.1
0x4552c  ldarg.0
0x4552d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::syncResponseFactory
0x45532  ldloc.3
0x45533  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x45538  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.TraceData::get_TraceCode()
0x4553d  ldloc.s  5
0x4553f  ldc.i4.1
0x45540  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponseFactory::GetErrorSyncResponse(int32 traceCode, string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeType)
0x45545  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.OutgoingEmailStats::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x4554a  leave.s  loc_4554C
0x4554c  ldarg.0
0x4554d  ldnull
0x4554e  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::set_CreateAttachmentAsyncResult(class [mscorlib]System.IAsyncResult value)
0x45553  ldarg.0
0x45554  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x45559  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x4555e  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::QueryForEarlyExitRequest()
0x45563  brfalse.s loc_4556D
0x45565  ldarg.0
0x45566  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::get_IsSynchronousEwsFcbEnabled()
0x4556b  brfalse.s loc_45584
0x4556d  ldloc.2
0x4556e  call     bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeHelper::IsAutoDiscoverNeeded(class Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType response)
0x45573  brfalse.s loc_45584
0x45575  ldarg.0
0x45576  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::TryAutoDiscover()
0x4557b  brfalse.s loc_45584
0x4557d  ldarg.0
0x4557e  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::BeginCreateAttachmentInternal()
0x45583  ret
0x45584  ldarg.0
0x45585  ldc.i4.0
0x45586  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::set_HasAutoDiscoveredAlready(bool value)
0x4558b  ldloc.2
0x4558c  brfalse.s loc_455DD
0x4558e  ldloc.2
0x4558f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x45594  brfalse.s loc_455DD
0x45596  ldloc.2
0x45597  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x4559c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x455a1  brfalse.s loc_455DD
0x455a3  ldloc.2
0x455a4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x455a9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x455ae  ldlen
0x455af  conv.i4
0x455b0  ldc.i4.1
0x455b1  blt.s    loc_455DD
0x455b3  ldloc.2
0x455b4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x455b9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x455be  ldc.i4.0
0x455bf  ldelem.ref
0x455c0  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ResponseClassType Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_ResponseClass()
0x455c5  brtrue.s loc_455DD
0x455c7  ldc.i4.3
0x455c8  ldarg.0
0x455c9  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x455ce  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x455d3  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventExecutionStatus [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_Status()
0x455d8  bne.un   loc_457DA
0x455dd  ldnull
0x455de  stloc.s  6
0x455e0  ldc.i4.3
0x455e1  ldarg.0
0x455e2  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x455e7  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x455ec  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventExecutionStatus [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_Status()
0x455f1  bne.un.s loc_4560C
0x455f3  ldarg.0
0x455f4  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::GetErrorInfoForPrematureResume()
0x455f9  stloc.3
0x455fa  ldloc.3
0x455fb  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x45600  callvirt instance string [Microsoft.Crm]Microsoft.Crm.TraceData::get_ErrorDetails()
0x45605  stloc.s  6
0x45607  br       loc_45768
0x4560c  ldloc.2
0x4560d  brtrue.s loc_4564C
0x4560f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x45614  ldstr    aErrorCreatingA_1// "Error creating attachment(s) for outgoi"...
0x45619  ldc.i4.1
0x4561a  newarr   [mscorlib]System.Object
0x4561f  dup
0x45620  ldc.i4.0
0x45621  ldloc.0
0x45622  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x45627  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x4562c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x45631  box      [mscorlib]System.Guid
0x45636  stelem.ref
0x45637  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4563c  stloc.s  6
0x4563e  ldarg.0
0x4563f  ldc.i4.4
0x45640  ldloc.s  6
0x45642  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x45647  br       loc_45768
0x4564c  ldloc.2
0x4564d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x45652  brfalse.s loc_45671
0x45654  ldloc.2
0x45655  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x4565a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x4565f  brfalse.s loc_45671
0x45661  ldloc.2
0x45662  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x45667  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x4566c  ldlen
0x4566d  conv.i4
0x4566e  ldc.i4.1
0x4566f  bge.s    loc_456C8
0x45671  ldarg.0
0x45672  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x45677  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x4567c  ldc.i4.s 0x1C
0x4567e  ldc.i4.1
0x4567f  ldc.i4.3
0x45680  ldc.i4.4
0x45681  ldc.i4.1
0x45682  ldnull
0x45683  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x45688  stloc.3
0x45689  ldstr    aInvalidRespons_1// "Invalid response obtained while creatin"...
0x4568e  ldloc.0
0x4568f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x45694  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x45699  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x4569e  box      [mscorlib]System.Guid
0x456a3  ldloc.3
0x456a4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x456a9  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.TraceData::get_TraceCode()
0x456ae  box      [mscorlib]System.Int32
0x456b3  call     string [mscorlib]System.String::Format(string, object, object)
0x456b8  stloc.s  6
0x456ba  ldarg.0
0x456bb  ldc.i4.1
0x456bc  ldloc.s  6
0x456be  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x456c3  br       loc_45768
0x456c8  ldloc.2
0x456c9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x456ce  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x456d3  ldc.i4.0
0x456d4  ldelem.ref
0x456d5  call     T0x2B000070
0x456da  stloc.s  8
0x456dc  ldstr    aErrorCreatingA_2// "Error creating attachment(s) for outgoi"...
0x456e1  ldloc.0
0x456e2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x456e7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x456ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x456f1  box      [mscorlib]System.Guid
0x456f6  ldloc.s  8
0x456f8  call     string [mscorlib]System.String::Format(string, object, object)
0x456fd  stloc.s  6
0x456ff  ldarg.0
0x45700  ldc.i4.1
0x45701  ldloc.s  6
0x45703  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x45708  call     class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeErrorCodeProcessor Microsoft.Crm.Asynchronous.EmailConnector.ExchangeErrorCodeProcessor::get_Instance()
0x4570d  ldloc.2
0x4570e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x45713  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x45718  ldc.i4.0
0x45719  ldelem.ref
0x4571a  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ResponseCodeType Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_ResponseCode()
0x4571f  ldloc.2
0x45720  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x45725  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x4572a  ldc.i4.0
0x4572b  ldelem.ref
0x4572c  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_MessageText()
0x45731  ldc.i4.1
0x45732  ldloc.2
0x45733  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x45738  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x4573d  ldc.i4.0
0x4573e  ldelem.ref
0x4573f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageTypeMessageXml Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_MessageXml()
0x45744  ldc.i4.1
0x45745  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeErrorCodeProcessor::GetErrorInfo(int32 errorCode, string responseMessage, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageTypeMessageXml responseMessageXml, [opt] valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType)
0x4574a  stloc.3
0x4574b  ldloc.3
0x4574c  brfalse.s loc_45768
0x4574e  ldloc.3
0x4574f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x45754  brfalse.s loc_45768
0x45756  ldloc.3
0x45757  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x4575c  ldloc.s  8
0x4575e  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatTraceLogErrorDetail(string message)
0x45763  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x45768  ldloc.3
0x45769  brfalse.s loc_4577A
  ... truncated ...
```
