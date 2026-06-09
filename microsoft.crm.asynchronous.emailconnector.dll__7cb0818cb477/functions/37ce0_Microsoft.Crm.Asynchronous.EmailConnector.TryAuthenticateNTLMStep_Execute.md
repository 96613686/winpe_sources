# Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::Execute

- ea: `0x37ce0`
- end: `0x38293`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::Execute`
- size: `1459`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x32970`
- `0x32980`
- `0x35770`
- `0x359a0`
- `0x359f0`
- `0x35a40`
- `0x35ac0`
- `0x35bb0`
- `0x35bc0`
- `0x35c10`
- `0x362c0`
- `0x36b60`
- `0x37030`
- `0x37060`
- `0x37140`
- `0x37ae0`
- `0x37b60`
- `0x37b70`
- `0x37ce0`
- `0x4e870`
- `0x4f410`
- `0x517c0`
- `0x71ff0`
- `0x81d30`

## string_xrefs

- `0x37d65`: `AUTH command received -ERR for mailbox: {0}`
- `0x38190`: `NTLM authentication failed during security negotiation for mailbox: {0}. hResult: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x37ce0  newobj   instance void <>c__DisplayClass9_0::.ctor()
0x37ce5  stloc.0
0x37ce6  ldloc.0
0x37ce7  ldarg.0
0x37ce8  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep <>c__DisplayClass9_0::<>4__this
0x37ced  ldc.i4.1
0x37cee  stloc.1
0x37cef  ldarg.0
0x37cf0  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep> Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::stepsList1
0x37cf5  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep>::get_Count()
0x37cfa  ldc.i4.0
0x37cfb  ble      loc_37E26
0x37d00  ldarg.0
0x37d01  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep> Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::stepsList1
0x37d06  ldc.i4.0
0x37d07  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep>::get_Item(!!T0)
0x37d0c  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::Execute()
0x37d11  stloc.1
0x37d12  ldloc.1
0x37d13  ldc.i4.1
0x37d14  beq.s    loc_37D18
0x37d16  ldloc.1
0x37d17  ret
0x37d18  ldarg.0
0x37d19  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x37d1e  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_ErrorResponseReturned()
0x37d23  brfalse.s loc_37D8F
0x37d25  ldc.i4.s 0x1B
0x37d27  ldc.i4.0
0x37d28  ldc.i4.s 9
0x37d2a  ldc.i4.4
0x37d2b  ldc.i4.0
0x37d2c  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo::.ctor(int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType operationType)
0x37d31  stloc.3
0x37d32  ldloc.3
0x37d33  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x37d38  ldarg.0
0x37d39  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x37d3e  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_ExchangeErrorResponse()
0x37d43  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x37d48  ldarg.0
0x37d49  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x37d4e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x37d53  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x37d58  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ErrorHandler()
0x37d5d  ldloc.3
0x37d5e  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler::HandleError(class Microsoft.Crm.Asynchronous.EmailConnector.IErrorInfo errorInfo)
0x37d63  ldarg.0
0x37d64  ldc.i4.2
0x37d65  ldstr    aAuthCommandRec// "AUTH command received -ERR for mailbox:"...
0x37d6a  ldc.i4.1
0x37d6b  newarr   [mscorlib]System.Object
0x37d70  dup
0x37d71  ldc.i4.0
0x37d72  ldarg.0
0x37d73  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x37d78  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x37d7d  ldstr    aMailboxid// "mailboxid"
0x37d82  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x37d87  stelem.ref
0x37d88  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x37d8d  ldc.i4.3
0x37d8e  ret
0x37d8f  ldarg.0
0x37d90  ldarg.0
0x37d91  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep> Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::stepsList1
0x37d96  ldc.i4.0
0x37d97  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep>::get_Item(!!T0)
0x37d9c  castclass Microsoft.Crm.Asynchronous.EmailConnector.SendCommandStep
0x37da1  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SendCommandStep::get_ReceivedLines()
0x37da6  stfld    string Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::receivedLine
0x37dab  ldc.i4.m1
0x37dac  ldarg.0
0x37dad  ldfld    string Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::receivedLine
0x37db2  ldstr    aNtlm// "NTLM"
0x37db7  ldc.i4.5
0x37db8  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x37dbd  bne.un.s loc_37E1A
0x37dbf  ldarg.0
0x37dc0  ldc.i4.1
0x37dc1  ldstr    aNtlmAuthentica// "NTLM authentication is not supported by"...
0x37dc6  ldc.i4.2
0x37dc7  newarr   [mscorlib]System.Object
0x37dcc  dup
0x37dcd  ldc.i4.0
0x37dce  ldarg.0
0x37dcf  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x37dd4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x37dd9  ldstr    aMailboxid// "mailboxid"
0x37dde  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x37de3  stelem.ref
0x37de4  dup
0x37de5  ldc.i4.1
0x37de6  ldarg.0
0x37de7  ldfld    string Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::receivedLine
0x37dec  stelem.ref
0x37ded  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x37df2  ldarg.0
0x37df3  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x37df8  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x37dfd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x37e02  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ErrorHandler()
0x37e07  ldc.i4.s 0x1B
0x37e09  ldc.i4.0
0x37e0a  ldc.i4.s 9
0x37e0c  ldc.i4.4
0x37e0d  ldc.i4.0
0x37e0e  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo::.ctor(int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType operationType)
0x37e13  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler::HandleError(class Microsoft.Crm.Asynchronous.EmailConnector.IErrorInfo errorInfo)
0x37e18  ldc.i4.3
0x37e19  ret
0x37e1a  ldarg.0
0x37e1b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep> Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::stepsList1
0x37e20  ldc.i4.0
0x37e21  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep>::RemoveAt(int32)
0x37e26  ldarg.0
0x37e27  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep> Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::stepsList2
0x37e2c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep>::get_Count()
0x37e31  ldc.i4.0
0x37e32  ble      loc_37F32
0x37e37  ldarg.0
0x37e38  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep> Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::stepsList2
0x37e3d  ldc.i4.0
0x37e3e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep>::get_Item(!!T0)
0x37e43  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::Execute()
0x37e48  stloc.1
0x37e49  ldloc.1
0x37e4a  ldc.i4.1
0x37e4b  beq.s    loc_37E4F
0x37e4d  ldloc.1
0x37e4e  ret
0x37e4f  ldarg.0
0x37e50  ldarg.0
0x37e51  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep> Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::stepsList2
0x37e56  ldc.i4.0
0x37e57  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep>::get_Item(!!T0)
0x37e5c  castclass Microsoft.Crm.Asynchronous.EmailConnector.SendCommandStep
0x37e61  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SendCommandStep::get_ReceivedLines()
0x37e66  stfld    string Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::receivedLine
0x37e6b  ldarg.0
0x37e6c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep> Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::stepsList2
0x37e71  ldc.i4.0
0x37e72  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep>::RemoveAt(int32)
0x37e77  ldarg.0
0x37e78  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x37e7d  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_ErrorResponseReturned()
0x37e82  brfalse.s loc_37EFF
0x37e84  ldarg.0
0x37e85  ldc.i4.2
0x37e86  ldstr    aPop3ServerDoes// "POP3 server does not support NTLM for m"...
0x37e8b  ldc.i4.2
0x37e8c  newarr   [mscorlib]System.Object
0x37e91  dup
0x37e92  ldc.i4.0
0x37e93  ldarg.0
0x37e94  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x37e99  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x37e9e  ldstr    aMailboxid// "mailboxid"
0x37ea3  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x37ea8  stelem.ref
0x37ea9  dup
0x37eaa  ldc.i4.1
0x37eab  ldarg.0
0x37eac  ldfld    string Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::receivedLine
0x37eb1  callvirt instance string [mscorlib]System.String::Trim()
0x37eb6  stelem.ref
0x37eb7  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x37ebc  ldc.i4.s 0x1B
0x37ebe  ldc.i4.0
0x37ebf  ldc.i4.s 9
0x37ec1  ldc.i4.4
0x37ec2  ldc.i4.0
0x37ec3  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo::.ctor(int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType operationType)
0x37ec8  stloc.s  5
0x37eca  ldloc.s  5
0x37ecc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x37ed1  ldarg.0
0x37ed2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::get_Pop3Client()
0x37ed7  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.Pop3Client::get_ExchangeErrorResponse()
0x37edc  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x37ee1  ldarg.0
0x37ee2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x37ee7  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x37eec  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x37ef1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ErrorHandler()
0x37ef6  ldloc.s  5
0x37ef8  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler::HandleError(class Microsoft.Crm.Asynchronous.EmailConnector.IErrorInfo errorInfo)
0x37efd  ldc.i4.3
0x37efe  ret
0x37eff  ldarg.0
0x37f00  ldfld    string Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::userName
0x37f05  ldc.i4.1
0x37f06  newarr   [mscorlib]System.Char
0x37f0b  dup
0x37f0c  ldc.i4.0
0x37f0d  ldc.i4.s 0x5C
0x37f0f  stelem.i2
0x37f10  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x37f15  stloc.s  4
0x37f17  ldc.i4.2
0x37f18  ldloc.s  4
0x37f1a  ldlen
0x37f1b  conv.i4
0x37f1c  bgt.s    loc_37F32
0x37f1e  ldarg.0
0x37f1f  ldloc.s  4
0x37f21  ldc.i4.0
0x37f22  ldelem.ref
0x37f23  stfld    string Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::domainName
0x37f28  ldarg.0
0x37f29  ldloc.s  4
0x37f2b  ldc.i4.1
0x37f2c  ldelem.ref
0x37f2d  stfld    string Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::userName
0x37f32  ldloc.0
0x37f33  ldflda   valuetype Microsoft.Crm.Asynchronous.EmailConnector.SECURITY_HANDLE <>c__DisplayClass9_0::phCredential
0x37f38  initobj  Microsoft.Crm.Asynchronous.EmailConnector.SECURITY_HANDLE
0x37f3e  ldloc.0
0x37f3f  ldflda   valuetype Microsoft.Crm.Asynchronous.EmailConnector.SECURITY_INTEGER <>c__DisplayClass9_0::ptsExpiry
0x37f44  initobj  Microsoft.Crm.Asynchronous.EmailConnector.SECURITY_INTEGER
0x37f4a  ldloc.0
0x37f4b  ldc.i4.0
0x37f4c  stfld    int32 <>c__DisplayClass9_0::res
0x37f51  ldarg.0
0x37f52  ldfld    class [mscorlib]System.Security.SecureString Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::password
0x37f57  ldloc.0
0x37f58  ldftn    instance void <>c__DisplayClass9_0::<Execute>b__0(native int unmanagedPassword)
0x37f5e  newobj   instance void class [mscorlib]System.Action`1<native int>::.ctor(object, native int)
0x37f63  call     void [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::SecureStringToIntPointer(class [mscorlib]System.Security.SecureString, class [mscorlib]System.Action`1<native int>)
0x37f68  ldloc.0
0x37f69  ldfld    int32 <>c__DisplayClass9_0::res
0x37f6e  brfalse.s loc_37FAF
0x37f70  ldarg.0
0x37f71  ldc.i4.1
0x37f72  ldstr    aTheSpecifiedNt// "The specified NTLM credentials could no"...
0x37f77  ldc.i4.2
0x37f78  newarr   [mscorlib]System.Object
0x37f7d  dup
0x37f7e  ldc.i4.0
0x37f7f  ldarg.0
0x37f80  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Pop3IncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::provider
0x37f85  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailProviderBase::get_Mailbox()
0x37f8a  ldstr    aMailboxid// "mailboxid"
0x37f8f  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x37f94  stelem.ref
0x37f95  dup
0x37f96  ldc.i4.1
0x37f97  ldloc.0
0x37f98  ldflda   int32 <>c__DisplayClass9_0::res
0x37f9d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37fa2  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x37fa7  stelem.ref
0x37fa8  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x37fad  ldc.i4.1
0x37fae  ret
0x37faf  ldloca.s 2
0x37fb1  ldc.i4   0x3000
0x37fb6  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.SecBufferDesc::.ctor(int32 bufferSize)
0x37fbb  ldloca.s 6
0x37fbd  ldc.i4.1
0x37fbe  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.SecBufferDesc::.ctor(int32 bufferSize)
0x37fc3  ldloca.s 7
0x37fc5  initobj  Microsoft.Crm.Asynchronous.EmailConnector.SECURITY_HANDLE
0x37fcb  ldloc.0
0x37fcc  ldflda   valuetype Microsoft.Crm.Asynchronous.EmailConnector.SECURITY_INTEGER <>c__DisplayClass9_0::ptsExpiry
0x37fd1  initobj  Microsoft.Crm.Asynchronous.EmailConnector.SECURITY_INTEGER
0x37fd7  ldc.i4.0
0x37fd8  stloc.s  8
0x37fda  ldloc.0
0x37fdb  ldflda   valuetype Microsoft.Crm.Asynchronous.EmailConnector.SECURITY_HANDLE <>c__DisplayClass9_0::phCredential
0x37fe0  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x37fe5  ldnull
0x37fe6  ldc.i4.0
0x37fe7  ldc.i4.0
0x37fe8  ldc.i4.0
0x37fe9  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x37fee  ldc.i4.0
0x37fef  ldloca.s 7
0x37ff1  ldloca.s 2
0x37ff3  ldloca.s 8
0x37ff5  ldloc.0
0x37ff6  ldflda   valuetype Microsoft.Crm.Asynchronous.EmailConnector.SECURITY_INTEGER <>c__DisplayClass9_0::ptsExpiry
0x37ffb  call     int32 Microsoft.Crm.Asynchronous.EmailConnector.NativeMethods::InitializeSecurityContext(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SECURITY_HANDLE& phCredential, native int phContext, string pszTargetName, int32 fContextReq, int32 Reserved1, int32 TargetDataRep, native int pInput, int32 Reserved2, [out] valuetype Microsoft.Crm.Asynchronous.EmailConnector.SECURITY_HANDLE& phNewContext, [out] valuetype Microsoft.Crm.Asynchronous.EmailConnector.SecBufferDesc& pOutput, [out] unsigned int32& pfContextAttr, [out] valuetype Microsoft.Crm.Asynchronous.EmailConnector.SECURITY_INTEGER& ptsExpiry)
0x38000  pop
0x38001  ldloca.s 2
0x38003  call     instance unsigned int8[] Microsoft.Crm.Asynchronous.EmailConnector.SecBufferDesc::GetBytes()
0x38008  stloc.s  9
0x3800a  ldloc.s  9
0x3800c  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x38011  stloc.s  0xA
0x38013  ldarg.0
0x38014  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep> Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::stepsList3
0x38019  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep>::get_Count()
0x3801e  ldc.i4.0
0x3801f  ble      loc_38131
0x38024  ldarg.0
0x38025  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep> Microsoft.Crm.Asynchronous.EmailConnector.TryAuthenticateNTLMStep::stepsList3
0x3802a  ldc.i4.0
0x3802b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ProcessingStep>::get_Item(!!T0)
0x38030  castclass Microsoft.Crm.Asynchronous.EmailConnector.SendCommandStep
  ... truncated ...
```
