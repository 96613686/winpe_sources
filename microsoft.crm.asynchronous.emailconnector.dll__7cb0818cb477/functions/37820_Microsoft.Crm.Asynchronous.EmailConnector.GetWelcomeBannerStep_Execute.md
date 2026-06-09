# Microsoft.Crm.Asynchronous.EmailConnector.GetWelcomeBannerStep::Execute

- ea: `0x37820`
- end: `0x378e3`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.GetWelcomeBannerStep::Execute`
- size: `195`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x32970`
- `0x32980`
- `0x35770`
- `0x35c10`
- `0x362c0`
- `0x36b60`
- `0x36bb0`
- `0x36bc0`
- `0x37030`
- `0x37060`
- `0x37140`
- `0x37580`
- `0x37820`
- `0x4e870`
- `0x4f410`
- `0x517c0`
- `0x71ff0`

## string_xrefs

- `0x37876`: `GetWelcomeBannerStep received -ERR for mailbox: {0}`
- `0x378c3`: `Welcome Banner Found : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x37820  ldc.i4.1
0x37821  stloc.0
0x37822  ldarg.0
0x37823  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::Execute()
0x37828  stloc.0
0x37829  ldarg.0
0x3782a  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x3782f  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_ErrorResponseReturned()
0x37834  brfalse.s loc_378A0
0x37836  ldc.i4.s 0x1B
0x37838  ldc.i4.0
0x37839  ldc.i4.s 9
0x3783b  ldc.i4.4
0x3783c  ldc.i4.0
0x3783d  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo::.ctor(int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType operationType)
0x37842  stloc.1
0x37843  ldloc.1
0x37844  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x37849  ldarg.0
0x3784a  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x3784f  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_ExchangeErrorResponse()
0x37854  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x37859  ldarg.0
0x3785a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x3785f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x37864  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x37869  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ErrorHandler()
0x3786e  ldloc.1
0x3786f  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler::HandleError(class Microsoft.Crm.Asynchronous.EmailConnector.IErrorInfo errorInfo)
0x37874  ldarg.0
0x37875  ldc.i4.2
0x37876  ldstr    aGetwelcomebann// "GetWelcomeBannerStep received -ERR for "...
0x3787b  ldc.i4.1
0x3787c  newarr   [mscorlib]System.Object
0x37881  dup
0x37882  ldc.i4.0
0x37883  ldarg.0
0x37884  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x37889  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x3788e  ldstr    aMailboxid// "mailboxid"
0x37893  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x37898  stelem.ref
0x37899  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3789e  ldc.i4.3
0x3789f  ret
0x378a0  ldloc.0
0x378a1  ldc.i4.1
0x378a2  bne.un.s loc_378E1
0x378a4  ldarg.0
0x378a5  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x378aa  ldarg.0
0x378ab  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ReadResponseStep::get_ReceivedLines()
0x378b0  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider::set_WelcomeBanner(string value)
0x378b5  ldarg.0
0x378b6  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x378bb  ldc.i4.1
0x378bc  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider::set_ConnectionState(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ConnectionState value)
0x378c1  ldarg.0
0x378c2  ldc.i4.3
0x378c3  ldstr    aWelcomeBannerF// "Welcome Banner Found : {0}"
0x378c8  ldc.i4.1
0x378c9  newarr   [mscorlib]System.Object
0x378ce  dup
0x378cf  ldc.i4.0
0x378d0  ldarg.0
0x378d1  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x378d6  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider::get_WelcomeBanner()
0x378db  stelem.ref
0x378dc  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x378e1  ldloc.0
0x378e2  ret
```
