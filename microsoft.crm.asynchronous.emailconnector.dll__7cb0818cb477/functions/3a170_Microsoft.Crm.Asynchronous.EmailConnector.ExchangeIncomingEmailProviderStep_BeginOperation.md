# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::BeginOperation

- ea: `0x3a170`
- end: `0x3a52c`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::BeginOperation`
- size: `956`
- prototype: ``
- caller_count: `14`
- callee_count: `25`
- tags: `broker_com_uri`

## callers

- `0x31b90`
- `0x39dc0`
- `0x3a530`
- `0x3b020`
- `0x3b850`
- `0x3c4b0`
- `0x3c630`
- `0x3ce00`
- `0x3dcb0`
- `0x3f6a0`
- `0x3f820`
- `0x3fc20`
- `0x408f0`
- `0x42d30`

## callees

- `0x7d10`
- `0x32970`
- `0x32980`
- `0x32a20`
- `0x32a50`
- `0x3a120`
- `0x3a170`
- `0x3ab40`
- `0x3abc0`
- `0x3aea0`
- `0x3aef0`
- `0x417a0`
- `0x41910`
- `0x41ba0`
- `0x42060`
- `0x42200`
- `0x42250`
- `0x42260`
- `0x4da80`
- `0x4e870`
- `0x4f410`
- `0x50ea0`
- `0x584c0`
- `0x58580`
- `0x71ff0`

## string_xrefs

- `0x3a3e8`: `Acquiring ACS token Fail: Please check if your tenantId is specified correctly`
- `0x3a401`: `Exception occurred in Begin call during Exchange incoming mailbox processing. Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3a170  ldarg.0
0x3a171  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a176  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3a17b  ldc.i4.1
0x3a17c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::set_WasCurrentStepExecuted(bool value)
0x3a181  ldarg.0
0x3a182  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::ContinueExecution()
0x3a187  brtrue.s loc_3A19C
0x3a189  ldarg.0
0x3a18a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a18f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3a194  ldc.i4.0
0x3a195  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::set_WasCurrentStepExecuted(bool value)
0x3a19a  ldc.i4.1
0x3a19b  ret
0x3a19c  ldarg.0
0x3a19d  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::stepStopwatch
0x3a1a2  callvirt instance void [System]System.Diagnostics.Stopwatch::Restart()
0x3a1a7  ldarg.0
0x3a1a8  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Initialize()
0x3a1ad  ldarg.0
0x3a1ae  ldc.i4.3
0x3a1af  ldstr    aRequestingThro// "Requesting throttle for mailbox {0}, or"...
0x3a1b4  ldc.i4.3
0x3a1b5  newarr   [mscorlib]System.Object
0x3a1ba  dup
0x3a1bb  ldc.i4.0
0x3a1bc  ldarg.0
0x3a1bd  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a1c2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3a1c7  ldstr    aMailboxid// "mailboxid"
0x3a1cc  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3a1d1  stelem.ref
0x3a1d2  dup
0x3a1d3  ldc.i4.1
0x3a1d4  ldarg.0
0x3a1d5  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a1da  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x3a1df  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x3a1e4  box      [mscorlib]System.Guid
0x3a1e9  stelem.ref
0x3a1ea  dup
0x3a1eb  ldc.i4.2
0x3a1ec  ldarg.0
0x3a1ed  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a1f2  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x3a1f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x3a1fc  box      [mscorlib]System.Guid
0x3a201  stelem.ref
0x3a202  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3a207  ldarg.0
0x3a208  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a20d  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IThrottledActivityProviderContext::RequestThrottle()
0x3a212  brtrue.s loc_3A270
0x3a214  ldarg.0
0x3a215  ldc.i4.3
0x3a216  ldstr    aThrottleCouldN// "Throttle could not be obtained for mail"...
0x3a21b  ldc.i4.3
0x3a21c  newarr   [mscorlib]System.Object
0x3a221  dup
0x3a222  ldc.i4.0
0x3a223  ldarg.0
0x3a224  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a229  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3a22e  ldstr    aMailboxid// "mailboxid"
0x3a233  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3a238  stelem.ref
0x3a239  dup
0x3a23a  ldc.i4.1
0x3a23b  ldarg.0
0x3a23c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a241  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x3a246  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x3a24b  box      [mscorlib]System.Guid
0x3a250  stelem.ref
0x3a251  dup
0x3a252  ldc.i4.2
0x3a253  ldarg.0
0x3a254  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a259  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x3a25e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x3a263  box      [mscorlib]System.Guid
0x3a268  stelem.ref
0x3a269  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3a26e  ldc.i4.2
0x3a26f  ret
0x3a270  nop
0x3a271  ldarg.0
0x3a272  ldc.i4.3
0x3a273  ldstr    aInvokingBeginc// "Invoking 'BeginCall' for operation '{0}"...
0x3a278  ldc.i4.4
0x3a279  newarr   [mscorlib]System.Object
0x3a27e  dup
0x3a27f  ldc.i4.0
0x3a280  ldarg.0
0x3a281  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::get_Name()
0x3a286  stelem.ref
0x3a287  dup
0x3a288  ldc.i4.1
0x3a289  ldarg.0
0x3a28a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a28f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3a294  ldstr    aMailboxid// "mailboxid"
0x3a299  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3a29e  stelem.ref
0x3a29f  dup
0x3a2a0  ldc.i4.2
0x3a2a1  ldarg.0
0x3a2a2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a2a7  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x3a2ac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x3a2b1  box      [mscorlib]System.Guid
0x3a2b6  stelem.ref
0x3a2b7  dup
0x3a2b8  ldc.i4.3
0x3a2b9  ldarg.0
0x3a2ba  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a2bf  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x3a2c4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x3a2c9  box      [mscorlib]System.Guid
0x3a2ce  stelem.ref
0x3a2cf  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3a2d4  ldarg.0
0x3a2d5  ldarg.0
0x3a2d6  ldftn    instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::<BeginOperation>b__6_0()
0x3a2dc  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x3a2e1  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::ExecuteWithRetry(class [mscorlib]System.Action action)
0x3a2e6  leave    loc_3A484
0x3a2eb  stloc.0
0x3a2ec  ldarg.0
0x3a2ed  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a2f2  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IThrottledActivityProviderContext::ReleaseThrottle()
0x3a2f7  ldc.i4.0
0x3a2f8  stloc.1
0x3a2f9  ldnull
0x3a2fa  stloc.2
0x3a2fb  ldarg.0
0x3a2fc  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a301  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext::get_EmailAccessConfiguration()
0x3a306  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Profile()
0x3a30b  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_ServerType()
0x3a310  ldc.i4.3
0x3a311  bne.un   loc_3A3FC
0x3a316  ldloc.0
0x3a317  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x3a31c  ldc.i4   0x80131509
0x3a321  bne.un   loc_3A3FC
0x3a326  ldarg.0
0x3a327  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a32c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3a331  newobj   instance void [Microsoft.Crm.Authentication.S2S]Microsoft.Crm.Authentication.S2S.CrmClientServicePrincipal::.ctor(valuetype [mscorlib]System.Guid)
0x3a336  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.X509SigningCredentials [Microsoft.Crm.Authentication.S2S]Microsoft.Crm.Authentication.S2S.ClientServicePrincipal::get_SigningCredentials()
0x3a33b  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [System.IdentityModel]System.IdentityModel.Tokens.X509SigningCredentials::get_Certificate()
0x3a340  callvirt instance valuetype [mscorlib]System.DateTime [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_NotAfter()
0x3a345  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x3a34a  call     int32 [mscorlib]System.DateTime::Compare(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3a34f  ldc.i4.0
0x3a350  clt
0x3a352  stloc.1
0x3a353  ldloc.1
0x3a354  brfalse.s loc_3A3C9
0x3a356  ldarg.0
0x3a357  ldc.i4.1
0x3a358  ldstr    aTheCertificate// "The certificate used is invalid and exp"...
0x3a35d  ldc.i4.1
0x3a35e  newarr   [mscorlib]System.Object
0x3a363  dup
0x3a364  ldc.i4.0
0x3a365  ldloc.0
0x3a366  ldarg.0
0x3a367  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a36c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3a371  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x3a376  stelem.ref
0x3a377  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3a37c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3a381  ldstr    aTheCertificate_0// "The certificate used is invalid and exp"...
0x3a386  ldc.i4.0
0x3a387  newarr   [mscorlib]System.Object
0x3a38c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3a391  ldloc.0
0x3a392  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x3a397  stloc.3
0x3a398  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x3a39d  ldarg.0
0x3a39e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a3a3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3a3a8  ldloc.3
0x3a3a9  ldc.i4.0
0x3a3aa  ldc.i4.0
0x3a3ab  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x3a3b0  stloc.2
0x3a3b1  ldloc.2
0x3a3b2  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3a3b7  ldloc.3
0x3a3b8  callvirt instance string [mscorlib]System.Object::ToString()
0x3a3bd  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatTraceLogErrorDetail(string message)
0x3a3c2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x3a3c7  br.s     loc_3A3FC
0x3a3c9  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x3a3ce  ldarg.0
0x3a3cf  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a3d4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3a3d9  ldloc.0
0x3a3da  ldc.i4.0
0x3a3db  ldc.i4.0
0x3a3dc  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x3a3e1  stloc.2
0x3a3e2  ldloc.2
0x3a3e3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3a3e8  ldstr    aAcquiringAcsTo// "Acquiring ACS token Fail: Please check "...
0x3a3ed  ldc.i4   0x400
0x3a3f2  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatExceptionMessage(string message, int32 maxLength)
0x3a3f7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x3a3fc  ldloc.1
0x3a3fd  brtrue.s loc_3A461
0x3a3ff  ldarg.0
0x3a400  ldc.i4.1
0x3a401  ldstr    aExceptionOccur_8// "Exception occurred in Begin call during"...
0x3a406  ldc.i4.1
0x3a407  newarr   [mscorlib]System.Object
0x3a40c  dup
0x3a40d  ldc.i4.0
0x3a40e  ldloc.0
0x3a40f  ldarg.0
0x3a410  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a415  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3a41a  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x3a41f  stelem.ref
0x3a420  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3a425  ldloc.2
0x3a426  brtrue.s loc_3A461
0x3a428  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x3a42d  ldarg.0
0x3a42e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a433  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3a438  ldloc.0
0x3a439  ldc.i4.0
0x3a43a  ldarg.0
0x3a43b  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a440  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_DefaultErrorType()
0x3a445  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x3a44a  stloc.2
0x3a44b  ldloc.2
0x3a44c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3a451  ldloc.0
0x3a452  callvirt instance string [mscorlib]System.Object::ToString()
0x3a457  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatTraceLogErrorDetail(string message)
0x3a45c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x3a461  ldarg.0
0x3a462  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a467  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3a46c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x3a471  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ErrorHandler()
0x3a476  ldloc.2
0x3a477  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler::HandleError(class Microsoft.Crm.Asynchronous.EmailConnector.IErrorInfo errorInfo)
0x3a47c  ldc.i4.1
0x3a47d  stloc.s  4
0x3a47f  leave    loc_3A529
0x3a484  ldarg.0
0x3a485  ldfld    class [mscorlib]System.IAsyncResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Result
0x3a48a  brfalse.s loc_3A4B6
0x3a48c  ldarg.0
0x3a48d  ldfld    class [mscorlib]System.IAsyncResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Result
0x3a492  callvirt instance bool [mscorlib]System.IAsyncResult::get_CompletedSynchronously()
0x3a497  brfalse.s loc_3A4B6
0x3a499  ldarg.0
0x3a49a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a49f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3a4a4  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_IsSynchronousEwsFcbEnabled()
0x3a4a9  brtrue.s loc_3A4B6
0x3a4ab  ldarg.0
0x3a4ac  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a4b1  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IThrottledActivityProviderContext::ReleaseThrottle()
0x3a4b6  ldarg.0
0x3a4b7  ldfld    class [mscorlib]System.IAsyncResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Result
0x3a4bc  brfalse.s loc_3A4CB
0x3a4be  ldarg.0
0x3a4bf  ldfld    class [mscorlib]System.IAsyncResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Result
0x3a4c4  callvirt instance bool [mscorlib]System.IAsyncResult::get_CompletedSynchronously()
0x3a4c9  brtrue.s loc_3A4DD
0x3a4cb  ldarg.0
0x3a4cc  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a4d1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3a4d6  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_IsSynchronousEwsFcbEnabled()
0x3a4db  brfalse.s loc_3A527
0x3a4dd  ldarg.0
0x3a4de  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::stepStopwatch
0x3a4e3  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x3a4e8  ldarg.0
0x3a4e9  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a4ee  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> Microsoft.Crm.Asynchronous.EmailConnector.ITelemetryData::get_StepDurationList()
0x3a4f3  brfalse.s loc_3A525
0x3a4f5  ldarg.0
0x3a4f6  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a4fb  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> Microsoft.Crm.Asynchronous.EmailConnector.ITelemetryData::get_StepDurationList()
0x3a500  ldarg.0
0x3a501  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3a506  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3a50b  ldarg.0
  ... truncated ...
```
