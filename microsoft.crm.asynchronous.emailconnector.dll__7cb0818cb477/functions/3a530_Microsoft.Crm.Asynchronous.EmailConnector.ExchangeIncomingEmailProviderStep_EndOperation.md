# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::EndOperation

- ea: `0x3a530`
- end: `0x3a987`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::EndOperation`
- size: `1111`
- prototype: ``
- caller_count: `2`
- callee_count: `36`
- tags: `broker_com_uri`

## callers

- `0x31b90`
- `0x3f6a0`

## callees

- `0x7d10`
- `0xb9b0`
- `0x32970`
- `0x32980`
- `0x32a20`
- `0x3a170`
- `0x3a530`
- `0x3ab40`
- `0x3ac40`
- `0x3aec0`
- `0x3aed0`
- `0x3aef0`
- `0x3af10`
- `0x417a0`
- `0x41910`
- `0x41b70`
- `0x41ba0`
- `0x41d80`
- `0x42000`
- `0x42060`
- `0x42090`
- `0x42200`
- `0x4da80`
- `0x4e870`
- `0x4f410`
- `0x50ea0`
- `0x516f0`
- `0x584c0`
- `0x58580`
- `0x71cf0`
- `0x71d00`
- `0x71e70`
- `0x71e80`
- `0x71e90`
- `0x71ea0`
- `0x71ff0`

## string_xrefs

- `0x3a6d4`: `Acquiring ACS token Fail: Please check if your tenantId is specified correctly`
- `0x3a6ed`: `Exception occurred while executing step during incoming email sync. Exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3a530  ldnull
0x3a531  stloc.0
0x3a532  ldarg.0
0x3a533  ldc.i4.0
0x3a534  stfld    bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::hasBatchError
0x3a539  ldarg.0
0x3a53a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a53f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3a544  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_IsSynchronousEwsFcbEnabled()
0x3a549  brtrue   loc_3A74F
0x3a54e  ldc.i4.3
0x3a54f  ldarg.0
0x3a550  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a555  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x3a55a  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventExecutionStatus [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_Status()
0x3a55f  bne.un.s loc_3A572
0x3a561  ldarg.0
0x3a562  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a567  ldarg.0
0x3a568  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::get_Name()
0x3a56d  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::AbortCurrentRequest(string name)
0x3a572  nop
0x3a573  ldarg.0
0x3a574  ldc.i4.3
0x3a575  ldstr    aInvokingEndcal// "Invoking 'EndCall' for operation '{0}',"...
0x3a57a  ldc.i4.4
0x3a57b  newarr   [mscorlib]System.Object
0x3a580  dup
0x3a581  ldc.i4.0
0x3a582  ldarg.0
0x3a583  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::get_Name()
0x3a588  stelem.ref
0x3a589  dup
0x3a58a  ldc.i4.1
0x3a58b  ldarg.0
0x3a58c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a591  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3a596  ldstr    aMailboxid// "mailboxid"
0x3a59b  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3a5a0  stelem.ref
0x3a5a1  dup
0x3a5a2  ldc.i4.2
0x3a5a3  ldarg.0
0x3a5a4  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a5a9  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x3a5ae  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x3a5b3  box      [mscorlib]System.Guid
0x3a5b8  stelem.ref
0x3a5b9  dup
0x3a5ba  ldc.i4.3
0x3a5bb  ldarg.0
0x3a5bc  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a5c1  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x3a5c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x3a5cb  box      [mscorlib]System.Guid
0x3a5d0  stelem.ref
0x3a5d1  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3a5d6  ldarg.0
0x3a5d7  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::EndCall()
0x3a5dc  leave    loc_3A74F
0x3a5e1  stloc.2
0x3a5e2  ldc.i4.0
0x3a5e3  stloc.3
0x3a5e4  ldarg.0
0x3a5e5  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a5ea  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext::get_EmailAccessConfiguration()
0x3a5ef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Profile()
0x3a5f4  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_ServerType()
0x3a5f9  ldc.i4.3
0x3a5fa  bne.un   loc_3A6E8
0x3a5ff  ldloc.2
0x3a600  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x3a605  ldc.i4   0x80131509
0x3a60a  bne.un   loc_3A6E8
0x3a60f  ldarg.0
0x3a610  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a615  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3a61a  newobj   instance void [Microsoft.Crm.Authentication.S2S]Microsoft.Crm.Authentication.S2S.CrmClientServicePrincipal::.ctor(valuetype [mscorlib]System.Guid)
0x3a61f  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.X509SigningCredentials [Microsoft.Crm.Authentication.S2S]Microsoft.Crm.Authentication.S2S.ClientServicePrincipal::get_SigningCredentials()
0x3a624  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [System.IdentityModel]System.IdentityModel.Tokens.X509SigningCredentials::get_Certificate()
0x3a629  callvirt instance valuetype [mscorlib]System.DateTime [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_NotAfter()
0x3a62e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x3a633  call     int32 [mscorlib]System.DateTime::Compare(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3a638  ldc.i4.0
0x3a639  clt
0x3a63b  stloc.3
0x3a63c  ldloc.3
0x3a63d  brfalse.s loc_3A6B5
0x3a63f  ldarg.0
0x3a640  ldc.i4.1
0x3a641  ldstr    aTheCertificate// "The certificate used is invalid and exp"...
0x3a646  ldc.i4.1
0x3a647  newarr   [mscorlib]System.Object
0x3a64c  dup
0x3a64d  ldc.i4.0
0x3a64e  ldloc.2
0x3a64f  ldarg.0
0x3a650  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a655  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3a65a  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x3a65f  stelem.ref
0x3a660  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3a665  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3a66a  ldstr    aTheCertificate_0// "The certificate used is invalid and exp"...
0x3a66f  ldc.i4.0
0x3a670  newarr   [mscorlib]System.Object
0x3a675  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3a67a  ldloc.2
0x3a67b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x3a680  stloc.s  4
0x3a682  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x3a687  ldarg.0
0x3a688  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a68d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3a692  ldloc.s  4
0x3a694  ldc.i4.0
0x3a695  ldc.i4.0
0x3a696  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x3a69b  stloc.0
0x3a69c  ldloc.0
0x3a69d  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3a6a2  ldloc.s  4
0x3a6a4  callvirt instance string [mscorlib]System.Object::ToString()
0x3a6a9  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatTraceLogErrorDetail(string message)
0x3a6ae  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x3a6b3  br.s     loc_3A6E8
0x3a6b5  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x3a6ba  ldarg.0
0x3a6bb  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a6c0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3a6c5  ldloc.2
0x3a6c6  ldc.i4.0
0x3a6c7  ldc.i4.0
0x3a6c8  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x3a6cd  stloc.0
0x3a6ce  ldloc.0
0x3a6cf  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3a6d4  ldstr    aAcquiringAcsTo// "Acquiring ACS token Fail: Please check "...
0x3a6d9  ldc.i4   0x400
0x3a6de  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatExceptionMessage(string message, int32 maxLength)
0x3a6e3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x3a6e8  ldloc.3
0x3a6e9  brtrue.s loc_3A74D
0x3a6eb  ldarg.0
0x3a6ec  ldc.i4.1
0x3a6ed  ldstr    aExceptionOccur_9// "Exception occurred while executing step"...
0x3a6f2  ldc.i4.1
0x3a6f3  newarr   [mscorlib]System.Object
0x3a6f8  dup
0x3a6f9  ldc.i4.0
0x3a6fa  ldloc.2
0x3a6fb  ldarg.0
0x3a6fc  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a701  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3a706  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x3a70b  stelem.ref
0x3a70c  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3a711  ldloc.0
0x3a712  brtrue.s loc_3A74D
0x3a714  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x3a719  ldarg.0
0x3a71a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a71f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3a724  ldloc.2
0x3a725  ldc.i4.0
0x3a726  ldarg.0
0x3a727  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a72c  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_DefaultErrorType()
0x3a731  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x3a736  stloc.0
0x3a737  ldloc.0
0x3a738  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3a73d  ldloc.2
0x3a73e  callvirt instance string [mscorlib]System.Object::ToString()
0x3a743  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatTraceLogErrorDetail(string message)
0x3a748  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x3a74d  leave.s  loc_3A74F
0x3a74f  ldarg.0
0x3a750  ldnull
0x3a751  stfld    class [mscorlib]System.IAsyncResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Result
0x3a756  ldarg.0
0x3a757  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a75c  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x3a761  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::QueryForEarlyExitRequest()
0x3a766  brfalse.s loc_3A77A
0x3a768  ldarg.0
0x3a769  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a76e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3a773  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_IsSynchronousEwsFcbEnabled()
0x3a778  brfalse.s loc_3A79B
0x3a77a  ldarg.0
0x3a77b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::get_Response()
0x3a780  call     bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeHelper::IsAutoDiscoverNeeded(class Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType response)
0x3a785  brfalse.s loc_3A79B
0x3a787  ldarg.0
0x3a788  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a78d  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::TryAutoDiscover()
0x3a792  brfalse.s loc_3A79B
0x3a794  ldarg.0
0x3a795  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::BeginOperation()
0x3a79a  ret
0x3a79b  ldc.i4.3
0x3a79c  ldarg.0
0x3a79d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a7a2  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x3a7a7  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventExecutionStatus [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_Status()
0x3a7ac  bne.un.s loc_3A7BA
0x3a7ae  ldarg.0
0x3a7af  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a7b4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::GetErrorInfoForPrematureResume()
0x3a7b9  stloc.0
0x3a7ba  ldloc.0
0x3a7bb  brtrue.s loc_3A7F3
0x3a7bd  ldarg.0
0x3a7be  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::IsInvalidResponse()
0x3a7c3  brfalse.s loc_3A7F3
0x3a7c5  ldarg.0
0x3a7c6  ldfld    bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::hasBatchError
0x3a7cb  brtrue.s loc_3A7F3
0x3a7cd  ldarg.0
0x3a7ce  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3a7d3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3a7d8  ldc.i4.s 0x1B
0x3a7da  ldarg.0
0x3a7db  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a7e0  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_DefaultErrorType()
0x3a7e5  ldc.i4.3
0x3a7e6  ldc.i4.4
0x3a7e7  ldc.i4.0
0x3a7e8  ldstr    aExchangerespon// "ExchangeResponseError"
0x3a7ed  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x3a7f2  stloc.0
0x3a7f3  ldloc.0
0x3a7f4  brfalse.s loc_3A81E
0x3a7f6  ldarg.0
0x3a7f7  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a7fc  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3a801  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x3a806  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_ErrorHandler()
0x3a80b  ldloc.0
0x3a80c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler::HandleError(class Microsoft.Crm.Asynchronous.EmailConnector.IErrorInfo errorInfo)
0x3a811  ldarg.0
0x3a812  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a817  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::SetProcessedState()
0x3a81c  ldc.i4.1
0x3a81d  ret
0x3a81e  ldarg.0
0x3a81f  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::ProcessResponse()
0x3a824  stloc.1
0x3a825  ldarg.0
0x3a826  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::stepStopwatch
0x3a82b  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x3a830  ldarg.0
0x3a831  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a836  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> Microsoft.Crm.Asynchronous.EmailConnector.ITelemetryData::get_StepDurationList()
0x3a83b  brfalse  loc_3A8F9
0x3a840  ldarg.0
0x3a841  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a846  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3a84b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x3a850  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3a855  ldstr    a012_0// "{0}{1}{2}"
0x3a85a  ldc.i4.3
0x3a85b  newarr   [mscorlib]System.Object
0x3a860  dup
0x3a861  ldc.i4.0
0x3a862  ldarg.0
0x3a863  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a868  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3a86d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x3a872  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_IndividualStepDuration()
0x3a877  stelem.ref
0x3a878  dup
0x3a879  ldc.i4.1
0x3a87a  ldarg.0
0x3a87b  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a880  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3a885  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x3a88a  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_IndividualStepDuration()
0x3a88f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3a894  brfalse.s loc_3A89D
0x3a896  ldsfld   string [mscorlib]System.String::Empty
0x3a89b  br.s     loc_3A8A2
0x3a89d  ldstr    asc_8925C// ","
0x3a8a2  stelem.ref
0x3a8a3  dup
0x3a8a4  ldc.i4.2
0x3a8a5  ldarg.0
0x3a8a6  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::stepStopwatch
0x3a8ab  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x3a8b0  stloc.s  5
0x3a8b2  ldloca.s 5
0x3a8b4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x3a8b9  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x3a8be  stelem.ref
0x3a8bf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3a8c4  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::set_IndividualStepDuration(string value)
0x3a8c9  ldarg.0
0x3a8ca  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3a8cf  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Dynamics.Telemetry]Microsoft.Dynamics.Telemetry.IJsonValueFormat>> Microsoft.Crm.Asynchronous.EmailConnector.ITelemetryData::get_StepDurationList()
  ... truncated ...
```
