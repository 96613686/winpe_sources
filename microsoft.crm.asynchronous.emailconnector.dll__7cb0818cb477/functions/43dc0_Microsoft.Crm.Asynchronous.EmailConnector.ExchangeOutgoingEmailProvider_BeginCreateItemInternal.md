# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::BeginCreateItemInternal

- ea: `0x43dc0`
- end: `0x44093`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::BeginCreateItemInternal`
- size: `723`
- prototype: ``
- caller_count: `2`
- callee_count: `32`
- tags: `broker_com_uri`

## callers

- `0x43da0`
- `0x440a0`

## callees

- `0x7d10`
- `0x17b10`
- `0x17b20`
- `0x17b30`
- `0x2ae10`
- `0x2ae20`
- `0x2ae40`
- `0x2ae60`
- `0x2aeb0`
- `0x41910`
- `0x420e0`
- `0x42170`
- `0x42250`
- `0x42260`
- `0x43600`
- `0x43720`
- `0x43780`
- `0x437a0`
- `0x43b40`
- `0x43dc0`
- `0x440a0`
- `0x44950`
- `0x44ce0`
- `0x46370`
- `0x46d70`
- `0x46e10`
- `0x47110`
- `0x4da80`
- `0x4f410`
- `0x50ea0`
- `0x58580`
- `0x822a0`

## string_xrefs

- `0x43e9e`: `CreateItem`
- `0x43ee0`: `CreateItem`

## pseudocode

```c

```

## disassembly

```asm
0x43dc0  newobj   instance void <>c__DisplayClass72_0::.ctor()
0x43dc5  stloc.0
0x43dc6  ldloc.0
0x43dc7  ldarg.0
0x43dc8  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider <>c__DisplayClass72_0::<>4__this
0x43dcd  ldloc.0
0x43dce  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.CreateItemType::.ctor()
0x43dd3  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateItemType <>c__DisplayClass72_0::request
0x43dd8  ldarg.0
0x43dd9  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_AnyEmailHasAttachment()
0x43dde  brtrue.s loc_43DEE
0x43de0  ldloc.0
0x43de1  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateItemType <>c__DisplayClass72_0::request
0x43de6  ldc.i4.1
0x43de7  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.CreateItemType::set_MessageDisposition(valuetype Microsoft.Crm.Asynchronous.EmailConnector.MessageDispositionType value)
0x43dec  br.s     loc_43DFA
0x43dee  ldloc.0
0x43def  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateItemType <>c__DisplayClass72_0::request
0x43df4  ldc.i4.0
0x43df5  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.CreateItemType::set_MessageDisposition(valuetype Microsoft.Crm.Asynchronous.EmailConnector.MessageDispositionType value)
0x43dfa  ldloc.0
0x43dfb  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateItemType <>c__DisplayClass72_0::request
0x43e00  ldc.i4.1
0x43e01  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.CreateItemType::set_MessageDispositionSpecified(bool value)
0x43e06  ldloc.0
0x43e07  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateItemType <>c__DisplayClass72_0::request
0x43e0c  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.NonEmptyArrayOfAllItemsType::.ctor()
0x43e11  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.CreateItemType::set_Items(class Microsoft.Crm.Asynchronous.EmailConnector.NonEmptyArrayOfAllItemsType value)
0x43e16  ldloc.0
0x43e17  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateItemType <>c__DisplayClass72_0::request
0x43e1c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.NonEmptyArrayOfAllItemsType Microsoft.Crm.Asynchronous.EmailConnector.CreateItemType::get_Items()
0x43e21  ldarg.0
0x43e22  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.MessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::GetMessagesFromWorkingSet()
0x43e27  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.NonEmptyArrayOfAllItemsType::set_Items(class Microsoft.Crm.Asynchronous.EmailConnector.ItemType[] value)
0x43e2c  ldarg.0
0x43e2d  ldc.i4.3
0x43e2e  ldstr    aBeginCreatingS// "Begin creating/sending a batch of {0} o"...
0x43e33  ldc.i4.1
0x43e34  newarr   [mscorlib]System.Object
0x43e39  dup
0x43e3a  ldc.i4.0
0x43e3b  ldloc.0
0x43e3c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateItemType <>c__DisplayClass72_0::request
0x43e41  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.NonEmptyArrayOfAllItemsType Microsoft.Crm.Asynchronous.EmailConnector.CreateItemType::get_Items()
0x43e46  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemType[] Microsoft.Crm.Asynchronous.EmailConnector.NonEmptyArrayOfAllItemsType::get_Items()
0x43e4b  ldlen
0x43e4c  conv.i4
0x43e4d  box      [mscorlib]System.Int32
0x43e52  stelem.ref
0x43e53  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x43e58  ldarg.0
0x43e59  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x43e5e  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IThrottledActivityProviderContext::RequestThrottle()
0x43e63  brtrue.s loc_43E67
0x43e65  ldc.i4.2
0x43e66  ret
0x43e67  ldarg.0
0x43e68  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::createItemStopwatch
0x43e6d  callvirt instance void [System]System.Diagnostics.Stopwatch::Restart()
0x43e72  ldarg.0
0x43e73  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::get_IsSynchronousEwsFcbEnabled()
0x43e78  brfalse.s loc_43EB4
0x43e7a  ldarg.0
0x43e7b  ldloc.0
0x43e7c  ldftn    instance void <>c__DisplayClass72_0::<BeginCreateItemInternal>b__0()
0x43e82  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x43e87  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::ExecuteWithRetry(class [mscorlib]System.Action action)
0x43e8c  ldarg.0
0x43e8d  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x43e92  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IThrottledActivityProviderContext::ReleaseThrottle()
0x43e97  ldarg.0
0x43e98  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::EndCreateItem()
0x43e9d  ldarg.0
0x43e9e  ldstr    aCreateitem// "CreateItem"
0x43ea3  ldarg.0
0x43ea4  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::createItemStopwatch
0x43ea9  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::ReportStepTiming(string stepName, class [System]System.Diagnostics.Stopwatch stopwatch)
0x43eae  stloc.1
0x43eaf  leave    loc_44091
0x43eb4  ldarg.0
0x43eb5  ldloc.0
0x43eb6  ldftn    instance void <>c__DisplayClass72_0::<BeginCreateItemInternal>b__1()
0x43ebc  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x43ec1  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::ExecuteWithRetry(class [mscorlib]System.Action action)
0x43ec6  ldarg.0
0x43ec7  ldarg.0
0x43ec8  call     instance class [mscorlib]System.IAsyncResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_CreateItemAsyncResult()
0x43ecd  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::HasOperationCompletedSynchronously(class [mscorlib]System.IAsyncResult asyncResult)
0x43ed2  brfalse.s loc_43EF7
0x43ed4  ldarg.0
0x43ed5  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x43eda  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IThrottledActivityProviderContext::ReleaseThrottle()
0x43edf  ldarg.0
0x43ee0  ldstr    aCreateitem// "CreateItem"
0x43ee5  ldarg.0
0x43ee6  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::createItemStopwatch
0x43eeb  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::ReportStepTiming(string stepName, class [System]System.Diagnostics.Stopwatch stopwatch)
0x43ef0  ldc.i4.1
0x43ef1  stloc.1
0x43ef2  leave    loc_44091
0x43ef7  leave    loc_4408F
0x43efc  stloc.2
0x43efd  ldarg.0
0x43efe  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x43f03  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IThrottledActivityProviderContext::ReleaseThrottle()
0x43f08  ldnull
0x43f09  stloc.3
0x43f0a  ldc.i4.0
0x43f0b  stloc.s  4
0x43f0d  ldarg.0
0x43f0e  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x43f13  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext::get_EmailAccessConfiguration()
0x43f18  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Profile()
0x43f1d  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_ServerType()
0x43f22  ldc.i4.3
0x43f23  bne.un   loc_43FDE
0x43f28  ldloc.2
0x43f29  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x43f2e  ldc.i4   0x80131509
0x43f33  bne.un   loc_43FDE
0x43f38  ldarg.0
0x43f39  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x43f3e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x43f43  newobj   instance void [Microsoft.Crm.Authentication.S2S]Microsoft.Crm.Authentication.S2S.CrmClientServicePrincipal::.ctor(valuetype [mscorlib]System.Guid)
0x43f48  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.X509SigningCredentials [Microsoft.Crm.Authentication.S2S]Microsoft.Crm.Authentication.S2S.ClientServicePrincipal::get_SigningCredentials()
0x43f4d  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [System.IdentityModel]System.IdentityModel.Tokens.X509SigningCredentials::get_Certificate()
0x43f52  callvirt instance valuetype [mscorlib]System.DateTime [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_NotAfter()
0x43f57  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x43f5c  call     int32 [mscorlib]System.DateTime::Compare(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x43f61  ldc.i4.0
0x43f62  clt
0x43f64  stloc.s  4
0x43f66  ldloc.s  4
0x43f68  brfalse.s loc_43FDE
0x43f6a  ldarg.0
0x43f6b  ldc.i4.1
0x43f6c  ldstr    aTheCertificate// "The certificate used is invalid and exp"...
0x43f71  ldc.i4.1
0x43f72  newarr   [mscorlib]System.Object
0x43f77  dup
0x43f78  ldc.i4.0
0x43f79  ldloc.2
0x43f7a  ldarg.0
0x43f7b  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x43f80  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x43f85  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x43f8a  stelem.ref
0x43f8b  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x43f90  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x43f95  ldstr    aTheCertificate_0// "The certificate used is invalid and exp"...
0x43f9a  ldc.i4.0
0x43f9b  newarr   [mscorlib]System.Object
0x43fa0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x43fa5  ldloc.2
0x43fa6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x43fab  stloc.s  5
0x43fad  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x43fb2  ldarg.0
0x43fb3  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x43fb8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x43fbd  ldloc.s  5
0x43fbf  ldc.i4.1
0x43fc0  ldc.i4.0
0x43fc1  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x43fc6  stloc.3
0x43fc7  ldloc.3
0x43fc8  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x43fcd  ldloc.s  5
0x43fcf  callvirt instance string [mscorlib]System.Object::ToString()
0x43fd4  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatTraceLogErrorDetail(string message)
0x43fd9  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x43fde  ldloc.s  4
0x43fe0  brtrue   loc_4408B
0x43fe5  ldarg.0
0x43fe6  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_ExchangeOutgoingEmailsWorkingSet()
0x43feb  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::GetEnumerator()
0x43ff0  stloc.s  6
0x43ff2  br.s     loc_4406F
0x43ff4  ldloca.s 6
0x43ff6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::get_Current()
0x43ffb  stloc.s  7
0x43ffd  ldarg.0
0x43ffe  ldc.i4.1
0x43fff  ldstr    aErrorCreatingT// "Error creating the outgoing mail item {"...
0x44004  ldc.i4.2
0x44005  newarr   [mscorlib]System.Object
0x4400a  dup
0x4400b  ldc.i4.0
0x4400c  ldloc.s  7
0x4400e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x44013  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x44018  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x4401d  box      [mscorlib]System.Guid
0x44022  stelem.ref
0x44023  dup
0x44024  ldc.i4.1
0x44025  ldloc.2
0x44026  ldarg.0
0x44027  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x4402c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x44031  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x44036  stelem.ref
0x44037  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x4403c  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x44041  ldarg.0
0x44042  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x44047  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x4404c  ldloc.2
0x4404d  ldc.i4.1
0x4404e  ldc.i4.1
0x4404f  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x44054  stloc.3
0x44055  ldarg.0
0x44056  ldloc.3
0x44057  ldloc.s  7
0x44059  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x4405e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_ErrorHandler()
0x44063  ldloc.s  7
0x44065  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail::get_OutgoingEmail()
0x4406a  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleOutgoingEmailError(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo errorInfo, class Microsoft.Crm.Asynchronous.EmailConnector.IErrorHandler errorHandler, class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity outgoingActivity)
0x4406f  ldloca.s 6
0x44071  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::MoveNext()
0x44076  brtrue   loc_43FF4
0x4407b  leave.s  loc_4408B
0x4407d  ldloca.s 6
0x4407f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>
0x44085  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4408a  endfinally
0x4408b  ldc.i4.1
0x4408c  stloc.1
0x4408d  leave.s  loc_44091
0x4408f  ldc.i4.0
0x44090  ret
0x44091  ldloc.1
0x44092  ret
```
