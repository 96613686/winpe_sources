# Microsoft.Crm.Asynchronous.EmailConnector.ReadMimeMessageStep::StartExecution

- ea: `0x37360`
- end: `0x37563`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ReadMimeMessageStep::StartExecution`
- size: `515`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `broker_com_uri`

## callees

- `0x306b0`
- `0x30710`
- `0x30740`
- `0x30990`
- `0x309f0`
- `0x30b00`
- `0x30f40`
- `0x30f50`
- `0x32970`
- `0x32980`
- `0x35770`
- `0x35c10`
- `0x36090`
- `0x360a0`
- `0x362c0`
- `0x36680`
- `0x36b40`
- `0x37030`
- `0x37060`
- `0x370c0`
- `0x37360`
- `0x377b0`
- `0x4e870`
- `0x4f410`
- `0x517c0`
- `0x71ff0`

## string_xrefs

- `0x373ff`: `EndExecute: POP3 server returned an error response on RETR command for mailbox: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x37360  ldarg.0
0x37361  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage Microsoft.Crm.Asynchronous.EmailConnector.ReadMimeMessageStep::emailMessage
0x37366  brtrue.s loc_3738E
0x37368  ldarg.0
0x37369  ldarg.0
0x3736a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x3736f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider::get_ProviderContext()
0x37374  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x37379  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage::.ctor(valuetype [mscorlib]System.Guid organizationId)
0x3737e  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage Microsoft.Crm.Asynchronous.EmailConnector.ReadMimeMessageStep::emailMessage
0x37383  ldarg.0
0x37384  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x37389  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::ResetValuesForNewResponse()
0x3738e  ldarg.0
0x3738f  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult Microsoft.Crm.Asynchronous.EmailConnector.ReadStep::StartExecution()
0x37394  stloc.0
0x37395  ldarg.0
0x37396  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x3739b  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_ErrorResponseReturned()
0x373a0  brfalse  loc_3742E
0x373a5  ldarg.0
0x373a6  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage Microsoft.Crm.Asynchronous.EmailConnector.ReadMimeMessageStep::emailMessage
0x373ab  brfalse.s loc_373BF
0x373ad  ldarg.0
0x373ae  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage Microsoft.Crm.Asynchronous.EmailConnector.ReadMimeMessageStep::emailMessage
0x373b3  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::Dispose()
0x373b8  ldarg.0
0x373b9  ldnull
0x373ba  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage Microsoft.Crm.Asynchronous.EmailConnector.ReadMimeMessageStep::emailMessage
0x373bf  ldc.i4.s 0x1B
0x373c1  ldc.i4.1
0x373c2  ldc.i4.s 9
0x373c4  ldc.i4.4
0x373c5  ldc.i4.0
0x373c6  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo::.ctor(int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType operationType)
0x373cb  stloc.1
0x373cc  ldloc.1
0x373cd  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x373d2  ldarg.0
0x373d3  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x373d8  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_ExchangeErrorResponse()
0x373dd  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x373e2  ldarg.0
0x373e3  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x373e8  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x373ed  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x373f2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ErrorHandler()
0x373f7  ldloc.1
0x373f8  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler::HandleError(class Microsoft.Crm.Asynchronous.EmailConnector.IErrorInfo errorInfo)
0x373fd  ldarg.0
0x373fe  ldc.i4.2
0x373ff  ldstr    aEndexecutePop3// "EndExecute: POP3 server returned an err"...
0x37404  ldc.i4.1
0x37405  newarr   [mscorlib]System.Object
0x3740a  dup
0x3740b  ldc.i4.0
0x3740c  ldarg.0
0x3740d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x37412  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x37417  ldstr    aMailboxid// "mailboxid"
0x3741c  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x37421  stelem.ref
0x37422  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x37427  ldc.i4.3
0x37428  stloc.0
0x37429  br       loc_37561
0x3742e  ldloc.0
0x3742f  ldc.i4.1
0x37430  bne.un   loc_37561
0x37435  ldarg.0
0x37436  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x3743b  callvirt instance unsigned int8[] Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_ReceivedBytes()
0x37440  ldlen
0x37441  conv.i4
0x37442  ldarg.0
0x37443  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x37448  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_BytesRead()
0x3744d  beq.s    loc_3747E
0x3744f  ldarg.0
0x37450  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x37455  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_BytesRead()
0x3745a  newarr   [mscorlib]System.Byte
0x3745f  stloc.2
0x37460  ldarg.0
0x37461  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x37466  callvirt instance unsigned int8[] Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_ReceivedBytes()
0x3746b  ldloc.2
0x3746c  ldarg.0
0x3746d  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x37472  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_BytesRead()
0x37477  call     void [mscorlib]System.Array::Copy(class [mscorlib]System.Array, class [mscorlib]System.Array, int32)
0x3747c  br.s     loc_3748A
0x3747e  ldarg.0
0x3747f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x37484  callvirt instance unsigned int8[] Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_ReceivedBytes()
0x37489  stloc.2
0x3748a  ldarg.0
0x3748b  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage Microsoft.Crm.Asynchronous.EmailConnector.ReadMimeMessageStep::emailMessage
0x37490  ldloc.2
0x37491  ldarg.0
0x37492  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_IsFurtherExecutionNecessary()
0x37497  ldc.i4.0
0x37498  ceq
0x3749a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::AppendDataToMimeMessage(unsigned int8[] data, bool closeAfterAppend)
0x3749f  ldarg.0
0x374a0  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_IsFurtherExecutionNecessary()
0x374a5  brtrue   loc_37561
0x374aa  ldarg.0
0x374ab  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage Microsoft.Crm.Asynchronous.EmailConnector.ReadMimeMessageStep::emailMessage
0x374b0  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::get_CharSet()
0x374b5  stloc.3
0x374b6  ldloc.3
0x374b7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x374bc  brtrue   loc_37561
0x374c1  ldloc.3
0x374c2  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x374c7  callvirt instance string [mscorlib]System.Text.Encoding::get_HeaderName()
0x374cc  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x374d1  brfalse  loc_37561
0x374d6  ldloc.3
0x374d7  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_ASCII()
0x374dc  callvirt instance string [mscorlib]System.Text.Encoding::get_HeaderName()
0x374e1  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x374e6  brfalse.s loc_37561
0x374e8  ldloc.3
0x374e9  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::GetEncoding(string)
0x374ee  ldarg.0
0x374ef  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage Microsoft.Crm.Asynchronous.EmailConnector.ReadMimeMessageStep::emailMessage
0x374f4  callvirt instance unsigned int8[] Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::GetEntireMessageData()
0x374f9  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x374fe  stloc.s  4
0x37500  ldarg.0
0x37501  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage Microsoft.Crm.Asynchronous.EmailConnector.ReadMimeMessageStep::emailMessage
0x37506  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::Dispose()
0x3750b  ldarg.0
0x3750c  ldloc.s  4
0x3750e  ldloc.3
0x3750f  ldarg.0
0x37510  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x37515  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider::get_ProviderContext()
0x3751a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3751f  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage::.ctor(string mimeData, string messageCharSet, valuetype [mscorlib]System.Guid organizationId)
0x37524  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage Microsoft.Crm.Asynchronous.EmailConnector.ReadMimeMessageStep::emailMessage
0x37529  ldarg.0
0x3752a  ldc.i4.3
0x3752b  ldstr    aGotTheEmailmes// "Got the emailmessage with messageId '{0"...
0x37530  ldc.i4.2
0x37531  newarr   [mscorlib]System.Object
0x37536  dup
0x37537  ldc.i4.0
0x37538  ldarg.0
0x37539  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage Microsoft.Crm.Asynchronous.EmailConnector.ReadMimeMessageStep::emailMessage
0x3753e  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::get_MessageId()
0x37543  stelem.ref
0x37544  dup
0x37545  ldc.i4.1
0x37546  ldarg.0
0x37547  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3EmailMessage Microsoft.Crm.Asynchronous.EmailConnector.ReadMimeMessageStep::emailMessage
0x3754c  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.MimeEmailMessage::get_TimeReceived()
0x37551  box      [mscorlib]System.DateTime
0x37556  stelem.ref
0x37557  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3755c  leave.s  loc_37561
0x3755e  pop
0x3755f  leave.s  loc_37561
0x37561  ldloc.0
0x37562  ret
```
