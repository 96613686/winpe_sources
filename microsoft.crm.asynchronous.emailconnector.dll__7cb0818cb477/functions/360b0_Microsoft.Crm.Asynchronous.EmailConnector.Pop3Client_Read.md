# Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::Read

- ea: `0x360b0`
- end: `0x3622c`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::Read`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x377b0`

## callees

- `0x32970`
- `0x32980`
- `0x35770`
- `0x35c20`
- `0x35d20`
- `0x360b0`
- `0x36230`
- `0x362d0`
- `0x362e0`
- `0x365b0`
- `0x4da80`
- `0x4e870`
- `0x50ea0`
- `0x71ff0`

## string_xrefs

- `0x3615d`: `EndRead: Exception occurred for mailbox: {0}. Details : {1}`
- `0x361eb`: `EndRead: Error response returned for mailbox: {0}. Text : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x360b0  ldarg.0
0x360b1  ldfld    unsigned int8[] Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::receivedBytes
0x360b6  brtrue.s loc_360C8
0x360b8  ldarg.0
0x360b9  ldc.i4   0x400
0x360be  newarr   [mscorlib]System.Byte
0x360c3  stfld    unsigned int8[] Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::receivedBytes
0x360c8  ldarg.2
0x360c9  ldc.i4.0
0x360ca  stind.i1
0x360cb  ldarg.0
0x360cc  ldarg.0
0x360cd  ldfld    class [mscorlib]System.IO.Stream Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::networkStream
0x360d2  ldarg.0
0x360d3  ldfld    unsigned int8[] Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::receivedBytes
0x360d8  ldc.i4.0
0x360d9  ldarg.0
0x360da  ldfld    unsigned int8[] Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::receivedBytes
0x360df  ldlen
0x360e0  conv.i4
0x360e1  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x360e6  stfld    int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::bytesRead
0x360eb  ldarg.0
0x360ec  ldfld    int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::bytesRead
0x360f1  ldc.i4.0
0x360f2  bgt.s    loc_360FF
0x360f4  ldstr    aThePop3ServerH// "The POP3 server has unexpectedly discon"...
0x360f9  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x360fe  throw
0x360ff  ldarg.0
0x36100  ldarg.0
0x36101  ldfld    int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::bytesReadSoFar
0x36106  ldarg.0
0x36107  ldfld    int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::bytesRead
0x3610c  add
0x3610d  stfld    int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::bytesReadSoFar
0x36112  ldarg.0
0x36113  ldarg.0
0x36114  ldarg.0
0x36115  ldfld    unsigned int8[] Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::singleLineTerminatingBytes
0x3611a  ldarg.0
0x3611b  ldfld    int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::singleLineTerminatingByteCount
0x36120  ldarg.3
0x36121  call     instance int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::PopulateTerminatingBytes(unsigned int8[] terminatingBytes, int32 terminatingBytesCount, bool enableLineTerminationTelemetry)
0x36126  stfld    int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::singleLineTerminatingByteCount
0x3612b  ldarg.0
0x3612c  ldarg.0
0x3612d  ldarg.0
0x3612e  ldfld    unsigned int8[] Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::multiLineTerminatingBytes
0x36133  ldarg.0
0x36134  ldfld    int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::multiLineTerminatingByteCount
0x36139  ldarg.3
0x3613a  call     instance int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::PopulateTerminatingBytes(unsigned int8[] terminatingBytes, int32 terminatingBytesCount, bool enableLineTerminationTelemetry)
0x3613f  stfld    int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::multiLineTerminatingByteCount
0x36144  leave.s  loc_361B3
0x36146  stloc.0
0x36147  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x3614c  ldarg.0
0x3614d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::organizationId
0x36152  ldloc.0
0x36153  ldc.i4.0
0x36154  ldc.i4.1
0x36155  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x3615a  stloc.1
0x3615b  ldarg.0
0x3615c  ldc.i4.1
0x3615d  ldstr    aEndreadExcepti// "EndRead: Exception occurred for mailbox"...
0x36162  ldc.i4.2
0x36163  newarr   [mscorlib]System.Object
0x36168  dup
0x36169  ldc.i4.0
0x3616a  ldarg.0
0x3616b  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::provider
0x36170  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x36175  ldstr    aMailboxid// "mailboxid"
0x3617a  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3617f  stelem.ref
0x36180  dup
0x36181  ldc.i4.1
0x36182  ldloc.0
0x36183  ldarg.0
0x36184  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::organizationId
0x36189  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x3618e  stelem.ref
0x3618f  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x36194  ldarg.0
0x36195  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::provider
0x3619a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x3619f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x361a4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ErrorHandler()
0x361a9  ldloc.1
0x361aa  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler::HandleError(class Microsoft.Crm.Asynchronous.EmailConnector.IErrorInfo errorInfo)
0x361af  ldc.i4.3
0x361b0  stloc.2
0x361b1  leave.s  loc_3622A
0x361b3  ldarg.0
0x361b4  ldfld    bool Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::isFirstReadChunk
0x361b9  brfalse.s loc_3621E
0x361bb  ldarg.0
0x361bc  ldc.i4.0
0x361bd  stfld    bool Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::isFirstReadChunk
0x361c2  ldarg.0
0x361c3  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::IsErrorResponseReturned()
0x361c8  brfalse.s loc_3621E
0x361ca  newobj   instance void [mscorlib]System.Text.ASCIIEncoding::.ctor()
0x361cf  ldarg.0
0x361d0  ldfld    unsigned int8[] Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::receivedBytes
0x361d5  ldc.i4.0
0x361d6  ldarg.0
0x361d7  ldfld    int32 Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::bytesReadSoFar
0x361dc  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[], int32, int32)
0x361e1  stloc.3
0x361e2  ldarg.0
0x361e3  ldloc.3
0x361e4  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::set_ExchangeErrorResponse(string value)
0x361e9  ldarg.0
0x361ea  ldc.i4.1
0x361eb  ldstr    aEndreadErrorRe// "EndRead: Error response returned for ma"...
0x361f0  ldc.i4.2
0x361f1  newarr   [mscorlib]System.Object
0x361f6  dup
0x361f7  ldc.i4.0
0x361f8  ldarg.0
0x361f9  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::provider
0x361fe  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x36203  ldstr    aMailboxid// "mailboxid"
0x36208  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3620d  stelem.ref
0x3620e  dup
0x3620f  ldc.i4.1
0x36210  ldloc.3
0x36211  stelem.ref
0x36212  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x36217  ldarg.0
0x36218  ldc.i4.1
0x36219  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::set_ErrorResponseReturned(bool value)
0x3621e  ldarg.2
0x3621f  ldarg.0
0x36220  ldarg.1
0x36221  ldarg.3
0x36222  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::IsNextReadRequired(bool singleCommand, bool enableLineTerminationTelemetry)
0x36227  stind.i1
0x36228  ldc.i4.1
0x36229  ret
0x3622a  ldloc.2
0x3622b  ret
```
