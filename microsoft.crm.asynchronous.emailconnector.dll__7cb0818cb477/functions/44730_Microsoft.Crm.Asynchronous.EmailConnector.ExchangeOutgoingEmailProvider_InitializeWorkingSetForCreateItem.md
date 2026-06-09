# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::InitializeWorkingSetForCreateItem

- ea: `0x44730`
- end: `0x4494e`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::InitializeWorkingSetForCreateItem`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `service_task, broker_com_uri`

## callers

- `0x43da0`

## callees

- `0x417a0`
- `0x420e0`
- `0x42110`
- `0x42120`
- `0x42130`
- `0x42140`
- `0x42150`
- `0x42160`
- `0x42170`
- `0x42190`
- `0x421c0`
- `0x43600`
- `0x43680`
- `0x43690`
- `0x43760`
- `0x43780`
- `0x43790`
- `0x44730`
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

- `0x44873`: `Cancel creating/sending of outgoing mail item {0} as the service is shutting down. Error TraceCode: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x44730  ldarg.0
0x44731  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::.ctor()
0x44736  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::set_ExchangeOutgoingEmailsWorkingSet(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail> value)
0x4473b  ldarg.0
0x4473c  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_ExchangeOutgoingEmails()
0x44741  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::GetEnumerator()
0x44746  stloc.0
0x44747  br       loc_44931
0x4474c  ldloca.s 0
0x4474e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::get_Current()
0x44753  stloc.1
0x44754  ldloc.1
0x44755  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailStatus Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_ExchangeStatus()
0x4475a  ldc.i4.1
0x4475b  and
0x4475c  brtrue   loc_44931
0x44761  ldloc.1
0x44762  ldarg.0
0x44763  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::syncResponseFactory
0x44768  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponseFactory::GetEmptySyncResponse()
0x4476d  ldarg.0
0x4476e  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x44773  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.OutgoingEmailStats::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail exchangeOutgoingEmail, class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse syncResponse, class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context)
0x44778  stloc.2
0x44779  ldloc.1
0x4477a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x4477f  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_HasError()
0x44784  brfalse.s loc_447B0
0x44786  ldloc.1
0x44787  dup
0x44788  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailStatus Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_ExchangeStatus()
0x4478d  ldc.i4.1
0x4478e  or
0x4478f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::set_ExchangeStatus(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailStatus value)
0x44794  ldloc.2
0x44795  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.OutgoingEmailStats::get_SyncResponse()
0x4479a  ldstr    aThisItemContai// "This item contains error. Skipped proce"...
0x4479f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse::set_TraceData(string value)
0x447a4  ldarg.0
0x447a5  ldloc.2
0x447a6  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::LogOutgoingItemStatistics(class Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.OutgoingEmailStats outgoingEmailStats)
0x447ab  br       loc_44931
0x447b0  ldloc.1
0x447b1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x447b6  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity::get_SenderMailbox()
0x447bb  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ContinueProcessing()
0x447c0  brtrue   loc_44857
0x447c5  ldloc.1
0x447c6  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x447cb  ldc.i4.1
0x447cc  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::set_FinalStateCode(int32 value)
0x447d1  ldloc.1
0x447d2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x447d7  ldc.i4.6
0x447d8  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::set_FinalStatusCode(int32 value)
0x447dd  ldloc.1
0x447de  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x447e3  ldc.i4.1
0x447e4  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::set_HasError(bool value)
0x447e9  ldloc.1
0x447ea  dup
0x447eb  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailStatus Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_ExchangeStatus()
0x447f0  ldc.i4.1
0x447f1  or
0x447f2  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::set_ExchangeStatus(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailStatus value)
0x447f7  ldc.i4.5
0x447f8  ldloc.1
0x447f9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x447fe  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity::get_SenderMailbox()
0x44803  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxProcessingResult Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ProcessingResult()
0x44808  bne.un.s loc_44816
0x4480a  ldloc.1
0x4480b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x44810  ldc.i4.0
0x44811  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity::set_IsDeliveryAttempted(bool value)
0x44816  ldloc.2
0x44817  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.OutgoingEmailStats::get_SyncResponse()
0x4481c  ldstr    aThisItemContai_0// "This item contains error with stateCode"...
0x44821  ldloc.1
0x44822  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x44827  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_FinalStateCode()
0x4482c  box      [mscorlib]System.Int32
0x44831  ldloc.1
0x44832  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x44837  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_FinalStatusCode()
0x4483c  box      [mscorlib]System.Int32
0x44841  call     string [mscorlib]System.String::Format(string, object, object)
0x44846  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse::set_TraceData(string value)
0x4484b  ldarg.0
0x4484c  ldloc.2
0x4484d  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::LogOutgoingItemStatistics(class Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.OutgoingEmailStats outgoingEmailStats)
0x44852  br       loc_44931
0x44857  ldarg.0
0x44858  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x4485d  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x44862  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::QueryForEarlyExitRequest()
0x44867  brfalse  loc_448FB
0x4486c  ldarg.0
0x4486d  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::GetErrorInfoForPrematureResume()
0x44872  stloc.3
0x44873  ldstr    aCancelCreating// "Cancel creating/sending of outgoing mai"...
0x44878  ldloc.1
0x44879  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x4487e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x44883  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x44888  box      [mscorlib]System.Guid
0x4488d  ldloc.3
0x4488e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x44893  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.TraceData::get_TraceCode()
0x44898  box      [mscorlib]System.Int32
0x4489d  call     string [mscorlib]System.String::Format(string, object, object)
0x448a2  stloc.s  4
0x448a4  ldarg.0
0x448a5  ldloc.3
0x448a6  ldloc.1
0x448a7  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x448ac  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_ErrorHandler()
0x448b1  ldloc.1
0x448b2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x448b7  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleOutgoingEmailError(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo errorInfo, class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler errorHandler, class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity outgoingActivity)
0x448bc  ldarg.0
0x448bd  ldc.i4.2
0x448be  ldloc.s  4
0x448c0  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x448c5  ldloc.1
0x448c6  dup
0x448c7  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailStatus Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_ExchangeStatus()
0x448cc  ldc.i4.1
0x448cd  or
0x448ce  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::set_ExchangeStatus(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailStatus value)
0x448d3  ldloc.2
0x448d4  ldarg.0
0x448d5  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::syncResponseFactory
0x448da  ldloc.3
0x448db  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x448e0  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.TraceData::get_TraceCode()
0x448e5  ldloc.s  4
0x448e7  ldc.i4.1
0x448e8  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponseFactory::GetErrorSyncResponse(int32 traceCode, string traceData, valuetype Microsoft.Crm.Asynchronous.EmailConnector.Common.ChangeType changeType)
0x448ed  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.OutgoingEmailStats::set_SyncResponse(class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse value)
0x448f2  ldarg.0
0x448f3  ldloc.2
0x448f4  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::LogOutgoingItemStatistics(class Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.OutgoingEmailStats outgoingEmailStats)
0x448f9  br.s     loc_44931
0x448fb  ldarg.0
0x448fc  ldc.i4.3
0x448fd  ldstr    aBeginCreatingS_0// "Begin creating/sending outgoing mail it"...
0x44902  ldc.i4.1
0x44903  newarr   [mscorlib]System.Object
0x44908  dup
0x44909  ldc.i4.0
0x4490a  ldloc.1
0x4490b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x44910  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x44915  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x4491a  box      [mscorlib]System.Guid
0x4491f  stelem.ref
0x44920  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x44925  ldarg.0
0x44926  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_ExchangeOutgoingEmailsWorkingSet()
0x4492b  ldloc.1
0x4492c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::Add(var<u1>)
0x44931  ldloca.s 0
0x44933  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::MoveNext()
0x44938  brtrue   loc_4474C
0x4493d  leave.s  loc_4494D
0x4493f  ldloca.s 0
0x44941  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>
0x44947  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4494c  endfinally
0x4494d  ret
```
