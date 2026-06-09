# Microsoft.Crm.Sandbox.SandboxListener`2::StartListening

- ea: `0x5680`
- end: `0x5a27`
- name: `Microsoft.Crm.Sandbox.SandboxListener`2::StartListening`
- size: `935`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1420`
- `0x14d0`
- `0x3080`
- `0x30f0`
- `0x4df0`
- `0x4f10`
- `0x5680`
- `0x78e0`
- `0x7d40`

## string_xrefs

- `0x5681`: `uriBuilder`
- `0x57eb`: `credentialsConfiguration`
- `0x5694`: `_serviceHost not null`
- `0x57a1`: `SandboxListener.StartListening: Uri: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5680  ldarg.1
0x5681  ldstr    aUribuilder// "uriBuilder"
0x5686  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x568b  ldarg.0
0x568c  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_serviceHost
0x5691  ldnull
0x5692  ceq
0x5694  ldstr    aServicehostNot// "_serviceHost not null"
0x5699  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x569e  ldarg.s  7
0x56a0  ldstr    aListenername// "listenerName"
0x56a5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x56aa  ldarg.0
0x56ab  ldarg.s  7
0x56ad  stfld    string class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_listenerName
0x56b2  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInSandboxWorkerContext()
0x56b7  brfalse.s loc_56C6
0x56b9  ldarg.1
0x56ba  ldstr    a127001// "127.0.0.1"
0x56bf  callvirt instance void [System]System.UriBuilder::set_Host(string)
0x56c4  br.s     loc_56D7
0x56c6  ldarg.1
0x56c7  ldc.i4.5
0x56c8  ldstr    aLocalhost// "localhost"
0x56cd  call     T0x2B000009
0x56d2  callvirt instance void [System]System.UriBuilder::set_Host(string)
0x56d7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x56dc  ldc.i4.s 0x26
0x56de  ldstr    aSandboxlistene// "SandboxListener.StartListening: Startin"...
0x56e3  ldc.i4.1
0x56e4  newarr   [mscorlib]System.Object
0x56e9  dup
0x56ea  ldc.i4.0
0x56eb  ldarg.0
0x56ec  ldfld    string class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_listenerName
0x56f1  stelem.ref
0x56f2  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x56f7  ldarg.s  4
0x56f9  newobj   instance void Microsoft.Crm.Sandbox.SandboxWcfConfiguration::.ctor(valuetype Microsoft.Crm.Sandbox.SandboxPropertyPrefix propertyPrefix)
0x56fe  stloc.0
0x56ff  ldstr    asc_FAA4// "-"
0x5704  stloc.1
0x5705  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x570a  ldc.i4.s 0x26
0x570c  ldstr    aSandboxlistene_0// "SandboxListener.StartListening: NetTcpB"...
0x5711  ldc.i4.0
0x5712  newarr   [mscorlib]System.Object
0x5717  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x571c  ldarg.2
0x571d  brtrue.s loc_5728
0x571f  ldc.i4.0
0x5720  newobj   instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::.ctor(valuetype [System.ServiceModel]System.ServiceModel.SecurityMode)
0x5725  stloc.3
0x5726  br.s     loc_5745
0x5728  ldc.i4.1
0x5729  newobj   instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::.ctor(valuetype [System.ServiceModel]System.ServiceModel.SecurityMode)
0x572e  stloc.3
0x572f  ldloc.3
0x5730  castclass [System.ServiceModel]System.ServiceModel.NetTcpBinding
0x5735  callvirt instance class [System.ServiceModel]System.ServiceModel.NetTcpSecurity [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_Security()
0x573a  callvirt instance class [System.ServiceModel]System.ServiceModel.TcpTransportSecurity [System.ServiceModel]System.ServiceModel.NetTcpSecurity::get_Transport()
0x573f  ldarg.2
0x5740  callvirt instance void [System.ServiceModel]System.ServiceModel.TcpTransportSecurity::set_ClientCredentialType(valuetype [System.ServiceModel]System.ServiceModel.TcpClientCredentialType)
0x5745  ldloc.3
0x5746  call     int32 [Microsoft.Crm]Microsoft.Crm.Timeouts::GetExtendedTimeout()
0x574b  ldc.i4   0x124F80
0x5750  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x5755  conv.r8
0x5756  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0x575b  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_ReceiveTimeout(valuetype [mscorlib]System.TimeSpan)
0x5760  ldc.i4.3
0x5761  ldc.i4.0
0x5762  call     T0x2B000008
0x5767  stloc.s  4
0x5769  ldloc.s  4
0x576b  ldc.i4.0
0x576c  ble.s    loc_5776
0x576e  ldarg.1
0x576f  ldloc.s  4
0x5771  callvirt instance void [System]System.UriBuilder::set_Port(int32)
0x5776  ldloc.0
0x5777  ldloc.3
0x5778  castclass [System.ServiceModel]System.ServiceModel.NetTcpBinding
0x577d  callvirt instance void Microsoft.Crm.Sandbox.SandboxWcfConfiguration::Apply(class [System.ServiceModel]System.ServiceModel.NetTcpBinding binding)
0x5782  ldarg.1
0x5783  ldloc.3
0x5784  callvirt instance string [System.ServiceModel]System.ServiceModel.Channels.Binding::get_Scheme()
0x5789  callvirt instance void [System]System.UriBuilder::set_Scheme(string)
0x578e  ldarg.1
0x578f  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x5794  callvirt instance string [mscorlib]System.Object::ToString()
0x5799  stloc.1
0x579a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x579f  ldc.i4.s 0x26
0x57a1  ldstr    aSandboxlistene_1// "SandboxListener.StartListening: Uri: {0"...
0x57a6  ldc.i4.1
0x57a7  newarr   [mscorlib]System.Object
0x57ac  dup
0x57ad  ldc.i4.0
0x57ae  ldloc.1
0x57af  stelem.ref
0x57b0  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x57b5  ldloc.1
0x57b6  newobj   instance void [System]System.Uri::.ctor(string)
0x57bb  stloc.s  5
0x57bd  ldarg.0
0x57be  ldtoken  var<u1>
0x57c3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x57c8  ldc.i4.1
0x57c9  newarr   [System]System.Uri
0x57ce  dup
0x57cf  ldc.i4.0
0x57d0  ldloc.s  5
0x57d2  stelem.ref
0x57d3  newobj   instance void [System.ServiceModel]System.ServiceModel.ServiceHost::.ctor(class [mscorlib]System.Type, class [System]System.Uri[])
0x57d8  stfld    class [System.ServiceModel]System.ServiceModel.ServiceHost class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_serviceHost
0x57dd  ldarg.2
0x57de  brfalse  loc_58B7
0x57e3  ldarg.2
0x57e4  ldc.i4.1
0x57e5  beq      loc_58B7
0x57ea  ldarg.3
0x57eb  ldstr    aCredentialscon// "credentialsConfiguration"
0x57f0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x57f5  ldarg.0
0x57f6  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_serviceHost
0x57fb  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials [System.ServiceModel]System.ServiceModel.ServiceHostBase::get_Credentials()
0x5800  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientServiceCredential [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials::get_ServiceCertificate()
0x5805  ldarg.3
0x5806  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientServiceCredential [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials::get_ServiceCertificate()
0x580b  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientServiceCredential::get_Certificate()
0x5810  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientServiceCredential::set_Certificate(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x5815  ldarg.2
0x5816  ldc.i4.2
0x5817  bne.un   loc_58B7
0x581c  ldarg.0
0x581d  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_serviceHost
0x5822  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials [System.ServiceModel]System.ServiceModel.ServiceHostBase::get_Credentials()
0x5827  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorServiceCredential [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials::get_ClientCertificate()
0x582c  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509ClientCertificateAuthentication [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorServiceCredential::get_Authentication()
0x5831  ldarg.3
0x5832  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorServiceCredential [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials::get_ClientCertificate()
0x5837  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509ClientCertificateAuthentication [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorServiceCredential::get_Authentication()
0x583c  callvirt instance valuetype [System.IdentityModel]System.ServiceModel.Security.X509CertificateValidationMode [System.ServiceModel]System.ServiceModel.Security.X509ClientCertificateAuthentication::get_CertificateValidationMode()
0x5841  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.X509ClientCertificateAuthentication::set_CertificateValidationMode(valuetype [System.IdentityModel]System.ServiceModel.Security.X509CertificateValidationMode)
0x5846  ldarg.0
0x5847  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_serviceHost
0x584c  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials [System.ServiceModel]System.ServiceModel.ServiceHostBase::get_Credentials()
0x5851  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorServiceCredential [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials::get_ClientCertificate()
0x5856  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509ClientCertificateAuthentication [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorServiceCredential::get_Authentication()
0x585b  ldarg.3
0x585c  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorServiceCredential [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials::get_ClientCertificate()
0x5861  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509ClientCertificateAuthentication [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorServiceCredential::get_Authentication()
0x5866  callvirt instance valuetype [System]System.Security.Cryptography.X509Certificates.X509RevocationMode [System.ServiceModel]System.ServiceModel.Security.X509ClientCertificateAuthentication::get_RevocationMode()
0x586b  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.X509ClientCertificateAuthentication::set_RevocationMode(valuetype [System]System.Security.Cryptography.X509Certificates.X509RevocationMode)
0x5870  ldarg.0
0x5871  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_serviceHost
0x5876  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials [System.ServiceModel]System.ServiceModel.ServiceHostBase::get_Credentials()
0x587b  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorServiceCredential [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials::get_ClientCertificate()
0x5880  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509ClientCertificateAuthentication [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorServiceCredential::get_Authentication()
0x5885  callvirt instance valuetype [System.IdentityModel]System.ServiceModel.Security.X509CertificateValidationMode [System.ServiceModel]System.ServiceModel.Security.X509ClientCertificateAuthentication::get_CertificateValidationMode()
0x588a  ldc.i4.4
0x588b  bne.un.s loc_58B7
0x588d  ldarg.0
0x588e  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_serviceHost
0x5893  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials [System.ServiceModel]System.ServiceModel.ServiceHostBase::get_Credentials()
0x5898  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorServiceCredential [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials::get_ClientCertificate()
0x589d  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509ClientCertificateAuthentication [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorServiceCredential::get_Authentication()
0x58a2  ldarg.3
0x58a3  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorServiceCredential [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials::get_ClientCertificate()
0x58a8  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509ClientCertificateAuthentication [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorServiceCredential::get_Authentication()
0x58ad  callvirt instance class [System.IdentityModel]System.IdentityModel.Selectors.X509CertificateValidator [System.ServiceModel]System.ServiceModel.Security.X509ClientCertificateAuthentication::get_CustomCertificateValidator()
0x58b2  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.X509ClientCertificateAuthentication::set_CustomCertificateValidator(class [System.IdentityModel]System.IdentityModel.Selectors.X509CertificateValidator)
0x58b7  ldarg.0
0x58b8  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_serviceHost
0x58bd  ldtoken  var<u1>
0x58c2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x58c7  ldloc.3
0x58c8  ldloc.s  5
0x58ca  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint [System.ServiceModel]System.ServiceModel.ServiceHost::AddServiceEndpoint(class [mscorlib]System.Type, class [System.ServiceModel]System.ServiceModel.Channels.Binding, class [System]System.Uri)
0x58cf  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Behaviors()
0x58d4  newobj   instance void [coreframework.communication.wcf]Microsoft.PowerApps.CoreFramework.Communication.Wcf.WcfCorrelationBehavior::.ctor()
0x58d9  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::Add(var<u1>)
0x58de  ldarg.0
0x58df  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_serviceHost
0x58e4  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceDescription [System.ServiceModel]System.ServiceModel.ServiceHostBase::get_Description()
0x58e9  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IServiceBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceDescription::get_Behaviors()
0x58ee  newobj   instance void Microsoft.Crm.Sandbox.SandboxErrorHandler::.ctor()
0x58f3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.IServiceBehavior>::Add(var<u1>)
0x58f8  ldarg.0
0x58f9  ldarg.s  4
0x58fb  ldloca.s 6
0x58fd  call     instance bool class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::TryGetOverrideThrottle(valuetype Microsoft.Crm.Sandbox.SandboxPropertyPrefix, class [System.ServiceModel]System.ServiceModel.Description.ServiceThrottlingBehavior&)
0x5902  brfalse.s loc_591B
0x5904  ldarg.0
0x5905  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_serviceHost
0x590a  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceDescription [System.ServiceModel]System.ServiceModel.ServiceHostBase::get_Description()
0x590f  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IServiceBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceDescription::get_Behaviors()
0x5914  ldloc.s  6
0x5916  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.IServiceBehavior>::Add(var<u1>)
0x591b  ldarg.0
0x591c  ldfld    class [System.ServiceModel]System.ServiceModel.ServiceHost class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_serviceHost
0x5921  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.CommunicationObject::Open()
0x5926  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x592b  ldc.i4.s 0x26
0x592d  ldstr    aSandboxlistene_2// "SandboxListener.StartListening: Started"...
0x5932  ldc.i4.1
0x5933  newarr   [mscorlib]System.Object
0x5938  dup
0x5939  ldc.i4.0
0x593a  ldarg.0
0x593b  ldfld    string class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_listenerName
0x5940  stelem.ref
0x5941  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x5946  leave    loc_59D6
0x594b  stloc.s  7
0x594d  ldloc.s  7
0x594f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5954  ldc.i4.s 0x21
0x5956  ldstr    aSandboxlistene_3// "SandboxListener.StartListening: EXCEPTI"...
0x595b  ldc.i4.1
0x595c  newarr   [mscorlib]System.Object
0x5961  dup
0x5962  ldc.i4.0
0x5963  ldloc.s  7
0x5965  stelem.ref
0x5966  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x596b  ldc.i4   0xC0004F12
0x5970  conv.u8
0x5971  ldarg.s  6
0x5973  ceq
0x5975  brfalse.s loc_5983
0x5977  ldsfld   class Microsoft.Crm.Sandbox.SandboxExponentialBackOff class Microsoft.Crm.Sandbox.SandboxListener`2<var<u1>, !!T0>::_eventBackoff
0x597c  callvirt instance bool Microsoft.Crm.Sandbox.SandboxExponentialBackOff::get_TimeUp()
0x5981  brfalse.s loc_59D4
0x5983  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x5988  stloc.s  8
0x598a  ldloc.s  8
0x598c  call     string Microsoft.Crm.Sandbox.SandboxUtility::get_EventSource()
0x5991  ldc.i4.1
0x5992  ldarg.s  6
0x5994  ldc.i4.3
0x5995  newarr   [mscorlib]System.Object
0x599a  dup
0x599b  ldc.i4.0
0x599c  call     string Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x59a1  stelem.ref
0x59a2  dup
0x59a3  ldc.i4.1
0x59a4  ldloc.1
0x59a5  stelem.ref
0x59a6  dup
0x59a7  ldc.i4.2
0x59a8  ldloc.s  7
0x59aa  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x59af  ldstr    asc_FC0C// ": "
0x59b4  ldloc.s  7
0x59b6  callvirt instance string [mscorlib]System.Exception::get_Message()
0x59bb  call     string [mscorlib]System.String::Concat(object, object, object)
0x59c0  stelem.ref
0x59c1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x59c6  leave.s  loc_59D4
0x59c8  ldloc.s  8
0x59ca  brfalse.s loc_59D3
0x59cc  ldloc.s  8
0x59ce  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x59d3  endfinally
0x59d4  rethrow
0x59d6  ldc.i4.1
0x59d7  stloc.2
0x59d8  ldc.i4   0x40004F01
0x59dd  conv.i8
0x59de  ldarg.s  5
0x59e0  bne.un.s loc_59ED
0x59e2  ldc.i4.4
0x59e3  ldc.i4.0
0x59e4  call     T0x2B000008
0x59e9  ldc.i4.1
0x59ea  cgt
0x59ec  stloc.2
0x59ed  ldloc.2
0x59ee  brfalse.s loc_5A26
0x59f0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x59f5  stloc.s  9
0x59f7  ldloc.s  9
0x59f9  call     string Microsoft.Crm.Sandbox.SandboxUtility::get_EventSource()
0x59fe  ldc.i4.4
0x59ff  ldarg.s  5
0x5a01  ldc.i4.2
0x5a02  newarr   [mscorlib]System.Object
0x5a07  dup
0x5a08  ldc.i4.0
0x5a09  call     string Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x5a0e  stelem.ref
0x5a0f  dup
0x5a10  ldc.i4.1
0x5a11  ldloc.1
0x5a12  stelem.ref
0x5a13  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x5a18  leave.s  loc_5A26
  ... truncated ...
```
