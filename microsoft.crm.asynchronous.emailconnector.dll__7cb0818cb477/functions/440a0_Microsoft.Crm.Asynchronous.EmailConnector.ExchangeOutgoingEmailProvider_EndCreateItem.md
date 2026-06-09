# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::EndCreateItem

- ea: `0x440a0`
- end: `0x44729`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::EndCreateItem`
- size: `1673`
- prototype: ``
- caller_count: `2`
- callee_count: `58`
- tags: `broker_com_uri`

## callers

- `0x43920`
- `0x43dc0`

## callees

- `0x7d10`
- `0x7d80`
- `0xb9b0`
- `0xfa50`
- `0x13fd0`
- `0x13ff0`
- `0x14070`
- `0x14090`
- `0x144f0`
- `0x18200`
- `0x23760`
- `0x242d0`
- `0x25060`
- `0x25110`
- `0x417a0`
- `0x41910`
- `0x420e0`
- `0x42170`
- `0x43600`
- `0x43660`
- `0x43670`
- `0x43680`
- `0x43690`
- `0x436d0`
- `0x43710`
- `0x43720`
- `0x43750`
- `0x43780`
- `0x437a0`
- `0x437b0`
- `0x43820`
- `0x43dc0`
- `0x440a0`
- `0x44ce0`
- `0x46320`
- `0x463f0`
- `0x46d70`
- `0x46e10`
- `0x46e60`
- `0x47110`
- `0x47b50`
- `0x47c00`
- `0x4da80`
- `0x4f410`
- `0x501e0`
- `0x50b40`
- `0x50ea0`
- `0x516f0`
- `0x51820`
- `0x584c0`

## string_xrefs

- `0x44106`: `CreateItem`
- `0x44211`: `Acquiring ACS token Fail: Please check if your tenantId is specified correctly`
- `0x440ab`: `Ending create item for {0} outgoing items.`
- `0x444f7`: `Outgoing activity {0} is created in exchange.`

## pseudocode

```c

```

## disassembly

```asm
0x440a0  ldarg.0
0x440a1  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.CreateItemResponseType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_CreateItemResponse()
0x440a6  stloc.0
0x440a7  ldnull
0x440a8  stloc.1
0x440a9  ldarg.0
0x440aa  ldc.i4.3
0x440ab  ldstr    aEndingCreateIt// "Ending create item for {0} outgoing ite"...
0x440b0  ldc.i4.1
0x440b1  newarr   [mscorlib]System.Object
0x440b6  dup
0x440b7  ldc.i4.0
0x440b8  ldarg.0
0x440b9  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_ExchangeOutgoingEmailsWorkingSet()
0x440be  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::get_Count()
0x440c3  box      [mscorlib]System.Int32
0x440c8  stelem.ref
0x440c9  call     instance void class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::HandleTraceForOutgoingActivityProvider(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x440ce  ldarg.0
0x440cf  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::get_IsSynchronousEwsFcbEnabled()
0x440d4  brtrue   loc_442A1
0x440d9  ldc.i4.3
0x440da  ldarg.0
0x440db  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x440e0  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x440e5  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventExecutionStatus [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_Status()
0x440ea  bne.un.s loc_440F2
0x440ec  ldarg.0
0x440ed  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::AbortCurrentRequest()
0x440f2  nop
0x440f3  ldarg.0
0x440f4  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeServiceBinding Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_ExchangeServiceBinding()
0x440f9  ldarg.0
0x440fa  call     instance class [mscorlib]System.IAsyncResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_CreateItemAsyncResult()
0x440ff  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.CreateItemResponseType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeServiceBinding::EndCreateItem(class [mscorlib]System.IAsyncResult asyncResult)
0x44104  stloc.0
0x44105  ldarg.0
0x44106  ldstr    aCreateitem// "CreateItem"
0x4410b  ldarg.0
0x4410c  ldfld    class [System]System.Diagnostics.Stopwatch Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::createItemStopwatch
0x44111  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::ReportStepTiming(string stepName, class [System]System.Diagnostics.Stopwatch stopwatch)
0x44116  leave    loc_442A1
0x4411b  stloc.3
0x4411c  ldc.i4.0
0x4411d  stloc.s  4
0x4411f  ldarg.0
0x44120  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x44125  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext::get_EmailAccessConfiguration()
0x4412a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Profile()
0x4412f  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_ServerType()
0x44134  ldc.i4.3
0x44135  bne.un   loc_44225
0x4413a  ldloc.3
0x4413b  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x44140  ldc.i4   0x80131509
0x44145  bne.un   loc_44225
0x4414a  ldarg.0
0x4414b  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x44150  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x44155  newobj   instance void [Microsoft.Crm.Authentication.S2S]Microsoft.Crm.Authentication.S2S.CrmClientServicePrincipal::.ctor(valuetype [mscorlib]System.Guid)
0x4415a  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.X509SigningCredentials [Microsoft.Crm.Authentication.S2S]Microsoft.Crm.Authentication.S2S.ClientServicePrincipal::get_SigningCredentials()
0x4415f  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [System.IdentityModel]System.IdentityModel.Tokens.X509SigningCredentials::get_Certificate()
0x44164  callvirt instance valuetype [mscorlib]System.DateTime [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_NotAfter()
0x44169  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x4416e  call     int32 [mscorlib]System.DateTime::Compare(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x44173  ldc.i4.0
0x44174  clt
0x44176  stloc.s  4
0x44178  ldloc.s  4
0x4417a  brfalse.s loc_441F2
0x4417c  ldarg.0
0x4417d  ldc.i4.1
0x4417e  ldstr    aTheCertificate// "The certificate used is invalid and exp"...
0x44183  ldc.i4.1
0x44184  newarr   [mscorlib]System.Object
0x44189  dup
0x4418a  ldc.i4.0
0x4418b  ldloc.3
0x4418c  ldarg.0
0x4418d  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x44192  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x44197  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x4419c  stelem.ref
0x4419d  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x441a2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x441a7  ldstr    aTheCertificate_0// "The certificate used is invalid and exp"...
0x441ac  ldc.i4.0
0x441ad  newarr   [mscorlib]System.Object
0x441b2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x441b7  ldloc.3
0x441b8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x441bd  stloc.s  5
0x441bf  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x441c4  ldarg.0
0x441c5  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x441ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x441cf  ldloc.s  5
0x441d1  ldc.i4.1
0x441d2  ldc.i4.0
0x441d3  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x441d8  stloc.1
0x441d9  ldloc.1
0x441da  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x441df  ldloc.s  5
0x441e1  callvirt instance string [mscorlib]System.Object::ToString()
0x441e6  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatTraceLogErrorDetail(string message)
0x441eb  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x441f0  br.s     loc_44225
0x441f2  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x441f7  ldarg.0
0x441f8  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x441fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x44202  ldloc.3
0x44203  ldc.i4.1
0x44204  ldc.i4.0
0x44205  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x4420a  stloc.1
0x4420b  ldloc.1
0x4420c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x44211  ldstr    aAcquiringAcsTo// "Acquiring ACS token Fail: Please check "...
0x44216  ldc.i4   0x400
0x4421b  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatExceptionMessage(string message, int32 maxLength)
0x44220  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x44225  ldloc.s  4
0x44227  brtrue.s loc_4429F
0x44229  ldarg.0
0x4422a  ldc.i4.1
0x4422b  ldstr    aErrorCreatingS// "Error creating/sending a batch of {0} o"...
0x44230  ldc.i4.2
0x44231  newarr   [mscorlib]System.Object
0x44236  dup
0x44237  ldc.i4.0
0x44238  ldarg.0
0x44239  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_ExchangeOutgoingEmailsWorkingSet()
0x4423e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::get_Count()
0x44243  box      [mscorlib]System.Int32
0x44248  stelem.ref
0x44249  dup
0x4424a  ldc.i4.1
0x4424b  ldloc.3
0x4424c  ldarg.0
0x4424d  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x44252  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x44257  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x4425c  stelem.ref
0x4425d  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x44262  ldloc.1
0x44263  brtrue.s loc_4429F
0x44265  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo> Microsoft.Crm.Asynchronous.EmailConnector.ExceptionProcessorFactory::CreateMailboxExceptionProcessor()
0x4426a  ldarg.0
0x4426b  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x44270  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x44275  ldloc.3
0x44276  ldc.i4.1
0x44277  ldc.i4.1
0x44278  callvirt instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.MailboxExceptionProcessor`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo>::GetErrorInfo(!!T0, valuetype [mscorlib]System.Guid, class [mscorlib]System.Exception, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType)
0x4427d  stloc.1
0x4427e  ldloc.1
0x4427f  brfalse.s loc_4429F
0x44281  ldloc.1
0x44282  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x44287  brfalse.s loc_4429F
0x44289  ldloc.1
0x4428a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x4428f  ldloc.3
0x44290  callvirt instance string [mscorlib]System.Object::ToString()
0x44295  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatTraceLogErrorDetail(string message)
0x4429a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x4429f  leave.s  loc_442A1
0x442a1  ldarg.0
0x442a2  ldnull
0x442a3  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::set_CreateItemAsyncResult(class [mscorlib]System.IAsyncResult value)
0x442a8  ldarg.0
0x442a9  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x442ae  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x442b3  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::QueryForEarlyExitRequest()
0x442b8  brfalse.s loc_442C2
0x442ba  ldarg.0
0x442bb  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::get_IsSynchronousEwsFcbEnabled()
0x442c0  brfalse.s loc_442D9
0x442c2  ldloc.0
0x442c3  call     bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeHelper::IsAutoDiscoverNeeded(class Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType response)
0x442c8  brfalse.s loc_442D9
0x442ca  ldarg.0
0x442cb  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::TryAutoDiscover()
0x442d0  brfalse.s loc_442D9
0x442d2  ldarg.0
0x442d3  call     instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionResult Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::BeginCreateItemInternal()
0x442d8  ret
0x442d9  ldloc.1
0x442da  brtrue.s loc_44354
0x442dc  ldloc.0
0x442dd  brfalse.s loc_44304
0x442df  ldloc.0
0x442e0  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x442e5  brfalse.s loc_44304
0x442e7  ldloc.0
0x442e8  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x442ed  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x442f2  brfalse.s loc_44304
0x442f4  ldloc.0
0x442f5  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x442fa  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x442ff  ldlen
0x44300  conv.i4
0x44301  ldc.i4.1
0x44302  bge.s    loc_44354
0x44304  ldarg.0
0x44305  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x4430a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x4430f  ldc.i4.s 0x1C
0x44311  ldc.i4.1
0x44312  ldc.i4.3
0x44313  ldc.i4.4
0x44314  ldc.i4.1
0x44315  ldnull
0x44316  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x4431b  stloc.1
0x4431c  ldarg.0
0x4431d  ldc.i4.1
0x4431e  ldstr    aInvalidRespons_0// "Invalid response obtained while creatin"...
0x44323  ldc.i4.2
0x44324  newarr   [mscorlib]System.Object
0x44329  dup
0x4432a  ldc.i4.0
0x4432b  ldarg.0
0x4432c  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_ExchangeOutgoingEmailsWorkingSet()
0x44331  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::get_Count()
0x44336  box      [mscorlib]System.Int32
0x4433b  stelem.ref
0x4433c  dup
0x4433d  ldc.i4.1
0x4433e  ldloc.1
0x4433f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x44344  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.TraceData::get_TraceCode()
0x44349  box      [mscorlib]System.Int32
0x4434e  stelem.ref
0x4434f  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x44354  ldc.i4.3
0x44355  ldarg.0
0x44356  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x4435b  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x44360  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventExecutionStatus [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_Status()
0x44365  bne.un.s loc_443A6
0x44367  ldarg.0
0x44368  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::GetErrorInfoForPrematureResume()
0x4436d  stloc.1
0x4436e  ldarg.0
0x4436f  ldc.i4.1
0x44370  ldstr    aIgnoringSucces// "Ignoring successful end of creating/sen"...
0x44375  ldc.i4.2
0x44376  newarr   [mscorlib]System.Object
0x4437b  dup
0x4437c  ldc.i4.0
0x4437d  ldarg.0
0x4437e  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_ExchangeOutgoingEmailsWorkingSet()
0x44383  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::get_Count()
0x44388  box      [mscorlib]System.Int32
0x4438d  stelem.ref
0x4438e  dup
0x4438f  ldc.i4.1
0x44390  ldloc.1
0x44391  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x44396  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.TraceData::get_TraceCode()
0x4439b  box      [mscorlib]System.Int32
0x443a0  stelem.ref
0x443a1  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x443a6  ldarg.0
0x443a7  ldc.i4.0
0x443a8  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::set_HasAutoDiscoveredAlready(bool value)
0x443ad  ldc.i4.m1
0x443ae  stloc.2
0x443af  ldarg.0
0x443b0  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmailProvider::get_ExchangeOutgoingEmailsWorkingSet()
0x443b5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::GetEnumerator()
0x443ba  stloc.s  6
0x443bc  br       loc_4470B
0x443c1  ldloca.s 6
0x443c3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail>::get_Current()
0x443c8  stloc.s  7
0x443ca  ldloc.2
0x443cb  ldc.i4.1
0x443cc  add
0x443cd  stloc.2
0x443ce  ldloc.s  7
0x443d0  ldarg.0
0x443d1  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponseFactory Microsoft.Crm.Asynchronous.EmailConnector.OutgoingEmailProviderBase::syncResponseFactory
0x443d6  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponseFactory::GetEmptySyncResponse()
0x443db  ldarg.0
0x443dc  call     instance var<u1> class Microsoft.Crm.Asynchronous.EmailConnector.OutgoingActivityProviderBase`1<class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext>::get_Context()
0x443e1  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemStatEvents.OutgoingEmailStats::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeOutgoingEmail exchangeOutgoingEmail, class Microsoft.Crm.Asynchronous.EmailConnector.Common.SyncResponse syncResponse, class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext context)
0x443e6  stloc.s  8
0x443e8  ldloc.1
0x443e9  brfalse  loc_444CB
0x443ee  ldloc.1
0x443ef  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo errorInfo)
0x443f4  stloc.s  0xA
0x443f6  ldloc.0
0x443f7  brfalse.s loc_4442B
0x443f9  ldloc.0
  ... truncated ...
```
