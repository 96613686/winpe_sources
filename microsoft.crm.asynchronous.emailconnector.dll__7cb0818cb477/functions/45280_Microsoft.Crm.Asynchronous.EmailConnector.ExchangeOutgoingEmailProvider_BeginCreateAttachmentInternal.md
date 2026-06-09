# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::BeginCreateAttachmentInternal

- ea: `0x45280`
- end: `0x453f0`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::BeginCreateAttachmentInternal`
- size: `368`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x45260`
- `0x453f0`

## callees

- `0x2a470`
- `0x2a490`
- `0x2a4a0`
- `0x420e0`
- `0x42170`
- `0x42250`
- `0x42260`
- `0x43600`
- `0x43640`
- `0x43660`
- `0x43780`
- `0x437c0`
- `0x43b40`
- `0x44ce0`
- `0x45280`
- `0x453f0`
- `0x46370`
- `0x46d70`
- `0x46e10`
- `0x47110`
- `0x4da80`
- `0x50ea0`
- `0x823c0`

## string_xrefs

- `0x4530d`: `CreateAttachment`
- `0x4534f`: `CreateAttachment`

## pseudocode

```c

```

## disassembly

```asm
0x45280  newobj   instance void <>c__DisplayClass83_0::.ctor()
0x45285  stloc.0
0x45286  ldloc.0
0x45287  ldarg.0
0x45288  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider <>c__DisplayClass83_0::<>4__this
0x4528d  ldarg.0
0x4528e  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_ExchangeOutgoingEmailsWorkingSet()
0x45293  ldc.i4.0
0x45294  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::get_Item(!!T0)
0x45299  stloc.1
0x4529a  ldloc.0
0x4529b  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.CreateAttachmentType::.ctor()
0x452a0  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateAttachmentType <>c__DisplayClass83_0::request
0x452a5  ldloc.0
0x452a6  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateAttachmentType <>c__DisplayClass83_0::request
0x452ab  ldloc.1
0x452ac  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_ItemId()
0x452b1  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.CreateAttachmentType::set_ParentItemId(class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType value)
0x452b6  ldloc.0
0x452b7  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateAttachmentType <>c__DisplayClass83_0::request
0x452bc  ldloc.1
0x452bd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.AttachmentType[] Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_Attachments()
0x452c2  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.CreateAttachmentType::set_Attachments(class Microsoft.Crm.Asynchronous.EmailConnector.AttachmentType[] value)
0x452c7  ldarg.0
0x452c8  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x452cd  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IThrottledActivityProviderContext::RequestThrottle()
0x452d2  brtrue.s loc_452D6
0x452d4  ldc.i4.2
0x452d5  ret
0x452d6  ldarg.0
0x452d7  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::createAttachmentStopwatch
0x452dc  callvirt instance void [System]System.Diagnostics.Stopwatch::Restart()
0x452e1  ldarg.0
0x452e2  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::get_IsSynchronousEwsFcbEnabled()
0x452e7  brfalse.s loc_45323
0x452e9  ldarg.0
0x452ea  ldloc.0
0x452eb  ldftn    instance void <>c__DisplayClass83_0::<BeginCreateAttachmentInternal>b__0()
0x452f1  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x452f6  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::ExecuteWithRetry(class [mscorlib]System.Action action)
0x452fb  ldarg.0
0x452fc  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x45301  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IThrottledActivityProviderContext::ReleaseThrottle()
0x45306  ldarg.0
0x45307  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::EndCreateAttachment()
0x4530c  ldarg.0
0x4530d  ldstr    aCreateattachme// "CreateAttachment"
0x45312  ldarg.0
0x45313  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::createAttachmentStopwatch
0x45318  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::ReportStepTiming(string stepName, class [System]System.Diagnostics.Stopwatch stopwatch)
0x4531d  stloc.2
0x4531e  leave    loc_453EE
0x45323  ldarg.0
0x45324  ldloc.0
0x45325  ldftn    instance void <>c__DisplayClass83_0::<BeginCreateAttachmentInternal>b__1()
0x4532b  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x45330  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::ExecuteWithRetry(class [mscorlib]System.Action action)
0x45335  ldarg.0
0x45336  ldarg.0
0x45337  call     instance class [mscorlib]System.IAsyncResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_CreateAttachmentAsyncResult()
0x4533c  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::HasOperationCompletedSynchronously(class [mscorlib]System.IAsyncResult asyncResult)
0x45341  brfalse.s loc_45366
0x45343  ldarg.0
0x45344  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x45349  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IThrottledActivityProviderContext::ReleaseThrottle()
0x4534e  ldarg.0
0x4534f  ldstr    aCreateattachme// "CreateAttachment"
0x45354  ldarg.0
0x45355  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::createAttachmentStopwatch
0x4535a  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::ReportStepTiming(string stepName, class [System]System.Diagnostics.Stopwatch stopwatch)
0x4535f  ldc.i4.1
0x45360  stloc.2
0x45361  leave    loc_453EE
0x45366  leave    loc_453EC
0x4536b  stloc.3
0x4536c  ldarg.0
0x4536d  ldc.i4.1
0x4536e  ldstr    aErrorCreatingA// "Error creating attachment(s) for outgoi"...
0x45373  ldc.i4.2
0x45374  newarr   [mscorlib]System.Object
0x45379  dup
0x4537a  ldc.i4.0
0x4537b  ldloc.1
0x4537c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x45381  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x45386  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x4538b  box      [mscorlib]System.Guid
0x45390  stelem.ref
0x45391  dup
0x45392  ldc.i4.1
0x45393  ldloc.3
0x45394  ldarg.0
0x45395  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x4539a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x4539f  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x453a4  stelem.ref
0x453a5  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x453aa  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x453af  ldarg.0
0x453b0  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x453b5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x453ba  ldloc.3
0x453bb  ldc.i4.1
0x453bc  ldc.i4.1
0x453bd  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x453c2  stloc.s  4
0x453c4  ldarg.0
0x453c5  ldloc.s  4
0x453c7  ldloc.1
0x453c8  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x453cd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_ErrorHandler()
0x453d2  ldloc.1
0x453d3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x453d8  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleOutgoingEmailError(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo errorInfo, class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler errorHandler, class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity outgoingActivity)
0x453dd  ldarg.0
0x453de  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x453e3  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IThrottledActivityProviderContext::ReleaseThrottle()
0x453e8  ldc.i4.1
0x453e9  stloc.2
0x453ea  leave.s  loc_453EE
0x453ec  ldc.i4.0
0x453ed  ret
0x453ee  ldloc.2
0x453ef  ret
```
