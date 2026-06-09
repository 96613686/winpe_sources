# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProvider::ReceiveEmails

- ea: `0x31b90`
- end: `0x31dce`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProvider::ReceiveEmails`
- size: `574`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `broker_com_uri`

## callees

- `0x31590`
- `0x31710`
- `0x31b90`
- `0x32680`
- `0x32970`
- `0x32980`
- `0x32a20`
- `0x32a40`
- `0x32d90`
- `0x32dd0`
- `0x32e10`
- `0x35710`
- `0x35770`
- `0x3a170`
- `0x3a530`
- `0x3aef0`
- `0x417a0`
- `0x42250`
- `0x4da80`
- `0x4e870`
- `0x516f0`
- `0x71ff0`
- `0x72070`

## string_xrefs

- `0x31d5e`: `Exception occurred during Exchange Incoming mailbox processing. Mailbox id: {0}, Organization id: {1}, Async Event id: {2}. Details : {3}`

## pseudocode

```c

```

## disassembly

```asm
0x31b90  ldc.i4.1
0x31b91  stloc.0
0x31b92  ldc.i4.0
0x31b93  stloc.1
0x31b94  ldarg.0
0x31b95  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeServiceBinding Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProvider::get_ExchangeServiceBinding()
0x31b9a  callvirt instance string [System.Web.Services]System.Web.Services.Protocols.WebClientProtocol::get_Url()
0x31b9f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x31ba4  brfalse.s loc_31BDF
0x31ba6  ldarg.0
0x31ba7  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::SetProcessedState()
0x31bac  ldarg.0
0x31bad  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x31bb2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x31bb7  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ErrorHandler()
0x31bbc  ldarg.0
0x31bbd  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x31bc2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x31bc7  ldc.i4.s 0xF
0x31bc9  ldc.i4.1
0x31bca  ldc.i4.8
0x31bcb  ldc.i4.4
0x31bcc  ldc.i4.0
0x31bcd  ldnull
0x31bce  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x31bd3  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler::HandleError(class Microsoft.Crm.Asynchronous.EmailConnector.IErrorInfo errorInfo)
0x31bd8  ldloc.0
0x31bd9  stloc.2
0x31bda  leave    loc_31DCC
0x31bdf  ldarg.0
0x31be0  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProvider::get_ProviderSteps()
0x31be5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep>::GetEnumerator()
0x31bea  stloc.3
0x31beb  br.s     loc_31C2A
0x31bed  ldloca.s 3
0x31bef  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep>::get_Current()
0x31bf4  stloc.s  4
0x31bf6  ldloc.s  4
0x31bf8  ldfld    class [mscorlib]System.IAsyncResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Result
0x31bfd  brfalse.s loc_31C2A
0x31bff  ldarg.0
0x31c00  ldc.i4.4
0x31c01  ldstr    aCallingEnd// "Calling End"
0x31c06  ldloc.s  4
0x31c08  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::get_Name()
0x31c0d  call     string [mscorlib]System.String::Concat(string, string)
0x31c12  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x31c17  ldloc.s  4
0x31c19  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::EndOperation()
0x31c1e  stloc.0
0x31c1f  ldloc.0
0x31c20  ldc.i4.1
0x31c21  beq.s    loc_31C2A
0x31c23  ldloc.0
0x31c24  stloc.2
0x31c25  leave    loc_31DCC
0x31c2a  ldloca.s 3
0x31c2c  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep>::MoveNext()
0x31c31  brtrue.s loc_31BED
0x31c33  leave.s  loc_31C43
0x31c35  ldloca.s 3
0x31c37  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep>
0x31c3d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31c42  endfinally
0x31c43  ldarg.0
0x31c44  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x31c49  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x31c4e  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ContinueProcessing()
0x31c53  brtrue.s loc_31C5C
0x31c55  ldc.i4.1
0x31c56  stloc.2
0x31c57  leave    loc_31DCC
0x31c5c  ldarg.0
0x31c5d  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x31c62  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x31c67  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::QueryForEarlyExitRequest()
0x31c6c  brfalse.s loc_31C90
0x31c6e  ldarg.0
0x31c6f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x31c74  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x31c79  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ErrorHandler()
0x31c7e  ldarg.0
0x31c7f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::GetErrorInfoForPrematureResume()
0x31c84  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler::HandleError(class Microsoft.Crm.Asynchronous.EmailConnector.IErrorInfo errorInfo)
0x31c89  ldc.i4.3
0x31c8a  stloc.2
0x31c8b  leave    loc_31DCC
0x31c90  ldc.i4.0
0x31c91  stloc.1
0x31c92  ldarg.0
0x31c93  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProvider::get_ProviderSteps()
0x31c98  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep>::GetEnumerator()
0x31c9d  stloc.3
0x31c9e  br.s     loc_31D16
0x31ca0  ldloca.s 3
0x31ca2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep>::get_Current()
0x31ca7  stloc.s  5
0x31ca9  ldloc.s  5
0x31cab  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::BeginOperation()
0x31cb0  stloc.0
0x31cb1  ldarg.0
0x31cb2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x31cb7  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_IsSynchronousEwsFcbEnabled()
0x31cbc  brfalse.s loc_31CF0
0x31cbe  ldloc.0
0x31cbf  ldc.i4.2
0x31cc0  beq.s    loc_31CF0
0x31cc2  ldarg.0
0x31cc3  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x31cc8  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_WasCurrentStepExecuted()
0x31ccd  brfalse.s loc_31CD7
0x31ccf  ldloc.s  5
0x31cd1  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::EndOperation()
0x31cd6  stloc.0
0x31cd7  ldarg.0
0x31cd8  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x31cdd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x31ce2  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ContinueProcessing()
0x31ce7  brtrue.s loc_31D16
0x31ce9  ldc.i4.1
0x31cea  stloc.2
0x31ceb  leave    loc_31DCC
0x31cf0  ldloc.0
0x31cf1  ldc.i4.1
0x31cf2  beq.s    loc_31CFB
0x31cf4  ldloc.0
0x31cf5  stloc.2
0x31cf6  leave    loc_31DCC
0x31cfb  ldloc.s  5
0x31cfd  ldfld    class [mscorlib]System.IAsyncResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Result
0x31d02  brfalse.s loc_31D16
0x31d04  ldloc.s  5
0x31d06  ldfld    class [mscorlib]System.IAsyncResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Result
0x31d0b  callvirt instance bool [mscorlib]System.IAsyncResult::get_CompletedSynchronously()
0x31d10  brfalse.s loc_31D16
0x31d12  ldc.i4.1
0x31d13  stloc.1
0x31d14  br.s     loc_31D1F
0x31d16  ldloca.s 3
0x31d18  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep>::MoveNext()
0x31d1d  brtrue.s loc_31CA0
0x31d1f  leave.s  loc_31D2F
0x31d21  ldloca.s 3
0x31d23  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep>
0x31d29  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31d2e  endfinally
0x31d2f  ldloc.1
0x31d30  brtrue   loc_31B94
0x31d35  ldarg.0
0x31d36  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x31d3b  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_IsSynchronousEwsFcbEnabled()
0x31d40  brfalse.s loc_31D4D
0x31d42  ldarg.0
0x31d43  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x31d48  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IThrottledActivityProviderContext::ReleaseThrottle()
0x31d4d  leave.s  loc_31DCA
0x31d4f  stloc.s  6
0x31d51  ldarg.0
0x31d52  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x31d57  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IThrottledActivityProviderContext::ReleaseThrottle()
0x31d5c  ldarg.0
0x31d5d  ldc.i4.1
0x31d5e  ldstr    aExceptionOccur_1// "Exception occurred during Exchange Inco"...
0x31d63  ldc.i4.4
0x31d64  newarr   [mscorlib]System.Object
0x31d69  dup
0x31d6a  ldc.i4.0
0x31d6b  ldarg.0
0x31d6c  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x31d71  ldstr    aMailboxid// "mailboxid"
0x31d76  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x31d7b  stelem.ref
0x31d7c  dup
0x31d7d  ldc.i4.1
0x31d7e  ldarg.0
0x31d7f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x31d84  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x31d89  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x31d8e  box      [mscorlib]System.Guid
0x31d93  stelem.ref
0x31d94  dup
0x31d95  ldc.i4.2
0x31d96  ldarg.0
0x31d97  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x31d9c  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x31da1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x31da6  box      [mscorlib]System.Guid
0x31dab  stelem.ref
0x31dac  dup
0x31dad  ldc.i4.3
0x31dae  ldloc.s  6
0x31db0  ldarg.0
0x31db1  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.IncomingActivityProviderBase::get_Context()
0x31db6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x31dbb  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x31dc0  stelem.ref
0x31dc1  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x31dc6  ldc.i4.1
0x31dc7  stloc.2
0x31dc8  leave.s  loc_31DCC
0x31dca  ldloc.0
0x31dcb  ret
0x31dcc  ldloc.2
0x31dcd  ret
```
