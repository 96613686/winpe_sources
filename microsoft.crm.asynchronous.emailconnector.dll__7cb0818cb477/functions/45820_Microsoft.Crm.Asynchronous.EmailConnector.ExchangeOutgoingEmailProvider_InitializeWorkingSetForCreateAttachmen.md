# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::InitializeWorkingSetForCreateAttachment

- ea: `0x45820`
- end: `0x45a25`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::InitializeWorkingSetForCreateAttachment`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `service_task, broker_com_uri`

## callers

- `0x45260`

## callees

- `0x417a0`
- `0x420e0`
- `0x42110`
- `0x42120`
- `0x42140`
- `0x42160`
- `0x42170`
- `0x42190`
- `0x421c0`
- `0x43600`
- `0x43640`
- `0x43680`
- `0x43690`
- `0x43760`
- `0x43780`
- `0x43790`
- `0x45820`
- `0x46e10`
- `0x46e60`
- `0x47110`
- `0x47b50`
- `0x47c00`
- `0x4f410`
- `0x71ec0`
- `0x72070`
- `0x7aad0`
- `0x7acf0`
- `0x7ad00`
- `0x81600`
- `0x81680`
- `0x816a0`

## string_xrefs

- `0x4592d`: `Cancel creating {0} attachment(s) for outgoing mail item {1} as the service is shutting down. Error TraceCode: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x45820  ldarg.0
0x45821  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::.ctor()
0x45826  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::set_ExchangeOutgoingEmailsWorkingSet(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail> value)
0x4582b  ldarg.0
0x4582c  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_ExchangeOutgoingEmails()
0x45831  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::GetEnumerator()
0x45836  stloc.0
0x45837  br       loc_45A08
0x4583c  ldloca.s 0
0x4583e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::get_Current()
0x45843  stloc.1
0x45844  ldloc.1
0x45845  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailStatus Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_ExchangeStatus()
0x4584a  ldc.i4.2
0x4584b  and
0x4584c  brtrue   loc_45A08
0x45851  ldloc.1
0x45852  ldarg.0
0x45853  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::syncResponseFactory
0x45858  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponseFactory::GetEmptySyncResponse()
0x4585d  ldarg.0
0x4585e  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x45863  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.OutgoingEmailStats::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail exchangeOutgoingEmail, class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse syncResponse, class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context)
0x45868  stloc.2
0x45869  ldloc.1
0x4586a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x4586f  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_HasError()
0x45874  brtrue.s loc_4587F
0x45876  ldloc.1
0x45877  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.AttachmentType[] Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_Attachments()
0x4587c  ldlen
0x4587d  brtrue.s loc_45892
0x4587f  ldloc.1
0x45880  dup
0x45881  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailStatus Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_ExchangeStatus()
0x45886  ldc.i4.2
0x45887  or
0x45888  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::set_ExchangeStatus(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailStatus value)
0x4588d  br       loc_45A08
0x45892  ldloc.1
0x45893  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x45898  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity::get_SenderMailbox()
0x4589d  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ContinueProcessing()
0x458a2  brtrue.s loc_45911
0x458a4  ldloc.1
0x458a5  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x458aa  ldc.i4.1
0x458ab  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::set_FinalStateCode(int32 value)
0x458b0  ldloc.1
0x458b1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x458b6  ldc.i4.6
0x458b7  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::set_FinalStatusCode(int32 value)
0x458bc  ldloc.1
0x458bd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x458c2  ldc.i4.1
0x458c3  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::set_HasError(bool value)
0x458c8  ldloc.1
0x458c9  dup
0x458ca  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailStatus Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_ExchangeStatus()
0x458cf  ldc.i4.2
0x458d0  or
0x458d1  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::set_ExchangeStatus(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailStatus value)
0x458d6  ldc.i4.5
0x458d7  ldloc.1
0x458d8  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x458dd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity::get_SenderMailbox()
0x458e2  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ProcessingResult()
0x458e7  bne.un.s loc_458F5
0x458e9  ldloc.1
0x458ea  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x458ef  ldc.i4.0
0x458f0  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity::set_IsDeliveryAttempted(bool value)
0x458f5  ldloc.2
0x458f6  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.OutgoingEmailStats::get_SyncResponse()
0x458fb  ldstr    aTheEmailHasAnE// "The email has an error. Skipped process"...
0x45900  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse::set_TraceData(string value)
0x45905  ldarg.0
0x45906  ldloc.2
0x45907  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::LogOutgoingItemStatistics(class Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.OutgoingEmailStats outgoingEmailStats)
0x4590c  br       loc_45A08
0x45911  ldarg.0
0x45912  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x45917  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x4591c  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::QueryForEarlyExitRequest()
0x45921  brfalse  loc_459C2
0x45926  ldarg.0
0x45927  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::GetErrorInfoForPrematureResume()
0x4592c  stloc.3
0x4592d  ldstr    aCancelCreating_0// "Cancel creating {0} attachment(s) for o"...
0x45932  ldloc.1
0x45933  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.AttachmentType[] Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_Attachments()
0x45938  ldlen
0x45939  conv.i4
0x4593a  box      [mscorlib]System.Int32
0x4593f  ldloc.1
0x45940  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x45945  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x4594a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x4594f  box      [mscorlib]System.Guid
0x45954  ldloc.3
0x45955  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x4595a  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.TraceData::get_TraceCode()
0x4595f  box      [mscorlib]System.Int32
0x45964  call     string [mscorlib]System.String::Format(string, object, object, object)
0x45969  stloc.s  4
0x4596b  ldarg.0
0x4596c  ldloc.3
0x4596d  ldloc.1
0x4596e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x45973  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_ErrorHandler()
0x45978  ldloc.1
0x45979  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x4597e  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleOutgoingEmailError(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo errorInfo, class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler errorHandler, class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity outgoingActivity)
0x45983  ldarg.0
0x45984  ldc.i4.2
0x45985  ldloc.s  4
0x45987  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x4598c  ldloc.2
0x4598d  ldarg.0
0x4598e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::syncResponseFactory
0x45993  ldloc.3
0x45994  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x45999  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.TraceData::get_TraceCode()
0x4599e  ldloc.s  4
0x459a0  ldc.i4.1
0x459a1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponseFactory::GetErrorSyncResponse(int32 traceCode, string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeType)
0x459a6  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.OutgoingEmailStats::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x459ab  ldarg.0
0x459ac  ldloc.2
0x459ad  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::LogOutgoingItemStatistics(class Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.OutgoingEmailStats outgoingEmailStats)
0x459b2  ldloc.1
0x459b3  dup
0x459b4  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailStatus Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_ExchangeStatus()
0x459b9  ldc.i4.2
0x459ba  or
0x459bb  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::set_ExchangeStatus(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailStatus value)
0x459c0  br.s     loc_45A08
0x459c2  ldarg.0
0x459c3  ldc.i4.3
0x459c4  ldstr    aBeginCreating0// "Begin creating {0} attachment(s) for ou"...
0x459c9  ldc.i4.2
0x459ca  newarr   [mscorlib]System.Object
0x459cf  dup
0x459d0  ldc.i4.0
0x459d1  ldloc.1
0x459d2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.AttachmentType[] Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_Attachments()
0x459d7  ldlen
0x459d8  conv.i4
0x459d9  box      [mscorlib]System.Int32
0x459de  stelem.ref
0x459df  dup
0x459e0  ldc.i4.1
0x459e1  ldloc.1
0x459e2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x459e7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x459ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x459f1  box      [mscorlib]System.Guid
0x459f6  stelem.ref
0x459f7  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x459fc  ldarg.0
0x459fd  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_ExchangeOutgoingEmailsWorkingSet()
0x45a02  ldloc.1
0x45a03  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::Add(var<u1>)
0x45a08  ldloca.s 0
0x45a0a  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::MoveNext()
0x45a0f  brtrue   loc_4583C
0x45a14  leave.s  loc_45A24
0x45a16  ldloca.s 0
0x45a18  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>
0x45a1e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45a23  endfinally
0x45a24  ret
```
