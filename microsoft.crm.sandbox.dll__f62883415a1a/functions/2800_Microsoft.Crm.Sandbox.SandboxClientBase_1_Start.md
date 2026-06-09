# Microsoft.Crm.Sandbox.SandboxClientBase`1::Start

- ea: `0x2800`
- end: `0x2a6b`
- name: `Microsoft.Crm.Sandbox.SandboxClientBase`1::Start`
- size: `619`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1450`
- `0x1460`
- `0x14a0`
- `0x14d0`
- `0x2800`
- `0x78e0`
- `0x7d40`

## string_xrefs

- `0x2819`: `uriBuilder`
- `0x2829`: `uriBuilder.Host`
- `0x28e0`: `credentialsConfiguration`
- `0x29ab`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x2a20`: `SandboxClientBase.Start: created WCF channel OK`

## pseudocode

```c

```

## disassembly

```asm
0x2800  ldarg.0
0x2801  ldfld    var<u1> class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::_proxy
0x2806  box      var<u1>
0x280b  ldnull
0x280c  ceq
0x280e  ldstr    aProxyIsNotNull// "_proxy is not null"
0x2813  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2818  ldarg.1
0x2819  ldstr    aUribuilder// "uriBuilder"
0x281e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2823  ldarg.1
0x2824  callvirt instance string [System]System.UriBuilder::get_Host()
0x2829  ldstr    aUribuilderHost// "uriBuilder.Host"
0x282e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2833  ldarg.s  4
0x2835  newobj   instance void Microsoft.Crm.Sandbox.SandboxWcfConfiguration::.ctor(valuetype Microsoft.Crm.Sandbox.SandboxPropertyPrefix propertyPrefix)
0x283a  stloc.0
0x283b  newobj   instance void class <>c__DisplayClass20_0<var<u1>>::.ctor()
0x2840  stloc.1
0x2841  ldloc.1
0x2842  ldarg.0
0x2843  stfld    class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>> class <>c__DisplayClass20_0<var<u1>>::<>4__this
0x2848  ldarg.2
0x2849  brtrue.s loc_2859
0x284b  ldloc.1
0x284c  ldc.i4.0
0x284d  newobj   instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::.ctor(valuetype [System.ServiceModel]System.ServiceModel.SecurityMode)
0x2852  stfld    class [System.ServiceModel]System.ServiceModel.Channels.Binding class <>c__DisplayClass20_0<var<u1>>::binding
0x2857  br.s     loc_2880
0x2859  ldloc.1
0x285a  ldc.i4.1
0x285b  newobj   instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::.ctor(valuetype [System.ServiceModel]System.ServiceModel.SecurityMode)
0x2860  stfld    class [System.ServiceModel]System.ServiceModel.Channels.Binding class <>c__DisplayClass20_0<var<u1>>::binding
0x2865  ldloc.1
0x2866  ldfld    class [System.ServiceModel]System.ServiceModel.Channels.Binding class <>c__DisplayClass20_0<var<u1>>::binding
0x286b  castclass [System.ServiceModel]System.ServiceModel.NetTcpBinding
0x2870  callvirt instance class [System.ServiceModel]System.ServiceModel.NetTcpSecurity [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_Security()
0x2875  callvirt instance class [System.ServiceModel]System.ServiceModel.TcpTransportSecurity [System.ServiceModel]System.ServiceModel.NetTcpSecurity::get_Transport()
0x287a  ldarg.2
0x287b  callvirt instance void [System.ServiceModel]System.ServiceModel.TcpTransportSecurity::set_ClientCredentialType(valuetype [System.ServiceModel]System.ServiceModel.TcpClientCredentialType)
0x2880  ldarg.0
0x2881  isinst   Microsoft.Crm.Sandbox.InternalSandboxSdkClient
0x2886  brfalse.s loc_28A8
0x2888  ldloc.1
0x2889  ldfld    class [System.ServiceModel]System.ServiceModel.Channels.Binding class <>c__DisplayClass20_0<var<u1>>::binding
0x288e  call     int32 [Microsoft.Crm]Microsoft.Crm.Timeouts::GetExtendedTimeout()
0x2893  ldc.i4   0x124F80
0x2898  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x289d  conv.r8
0x289e  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0x28a3  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_CloseTimeout(valuetype [mscorlib]System.TimeSpan)
0x28a8  ldc.i4.3
0x28a9  ldc.i4.0
0x28aa  call     T0x2B000008
0x28af  stloc.2
0x28b0  ldloc.2
0x28b1  ldc.i4.0
0x28b2  ble.s    loc_28BB
0x28b4  ldarg.1
0x28b5  ldloc.2
0x28b6  callvirt instance void [System]System.UriBuilder::set_Port(int32)
0x28bb  ldloc.0
0x28bc  ldloc.1
0x28bd  ldfld    class [System.ServiceModel]System.ServiceModel.Channels.Binding class <>c__DisplayClass20_0<var<u1>>::binding
0x28c2  castclass [System.ServiceModel]System.ServiceModel.NetTcpBinding
0x28c7  callvirt instance void Microsoft.Crm.Sandbox.SandboxWcfConfiguration::Apply(class [System.ServiceModel]System.ServiceModel.NetTcpBinding binding)
0x28cc  ldloc.1
0x28cd  ldfld    class [System.ServiceModel]System.ServiceModel.Channels.Binding class <>c__DisplayClass20_0<var<u1>>::binding
0x28d2  newobj   instance void class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<var<u1>>::.ctor(class [System.ServiceModel]System.ServiceModel.Channels.Binding)
0x28d7  stloc.3
0x28d8  ldarg.2
0x28d9  brfalse.s loc_2953
0x28db  ldarg.2
0x28dc  ldc.i4.1
0x28dd  beq.s    loc_2953
0x28df  ldarg.3
0x28e0  ldstr    aCredentialscon// "credentialsConfiguration"
0x28e5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x28ea  ldloc.3
0x28eb  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials [System.ServiceModel]System.ServiceModel.ChannelFactory::get_Credentials()
0x28f0  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_ServiceCertificate()
0x28f5  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential::get_Authentication()
0x28fa  ldarg.3
0x28fb  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_ServiceCertificate()
0x2900  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential::get_Authentication()
0x2905  callvirt instance valuetype [System.IdentityModel]System.ServiceModel.Security.X509CertificateValidationMode [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication::get_CertificateValidationMode()
0x290a  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication::set_CertificateValidationMode(valuetype [System.IdentityModel]System.ServiceModel.Security.X509CertificateValidationMode)
0x290f  ldloc.3
0x2910  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials [System.ServiceModel]System.ServiceModel.ChannelFactory::get_Credentials()
0x2915  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_ServiceCertificate()
0x291a  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential::get_Authentication()
0x291f  ldarg.3
0x2920  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_ServiceCertificate()
0x2925  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential::get_Authentication()
0x292a  callvirt instance valuetype [System]System.Security.Cryptography.X509Certificates.X509RevocationMode [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication::get_RevocationMode()
0x292f  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication::set_RevocationMode(valuetype [System]System.Security.Cryptography.X509Certificates.X509RevocationMode)
0x2934  ldarg.2
0x2935  ldc.i4.2
0x2936  bne.un.s loc_2953
0x2938  ldloc.3
0x2939  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials [System.ServiceModel]System.ServiceModel.ChannelFactory::get_Credentials()
0x293e  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_ClientCertificate()
0x2943  ldarg.3
0x2944  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_ClientCertificate()
0x2949  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorClientCredential::get_Certificate()
0x294e  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorClientCredential::set_Certificate(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x2953  ldarg.0
0x2954  ldloc.3
0x2955  call     instance void class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::AddBehaviors(class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<var<u1>>)
0x295a  ldloc.3
0x295b  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.CommunicationObject::Open()
0x2960  ldarg.1
0x2961  ldloc.1
0x2962  ldfld    class [System.ServiceModel]System.ServiceModel.Channels.Binding class <>c__DisplayClass20_0<var<u1>>::binding
0x2967  callvirt instance string [System.ServiceModel]System.ServiceModel.Channels.Binding::get_Scheme()
0x296c  callvirt instance void [System]System.UriBuilder::set_Scheme(string)
0x2971  ldarg.1
0x2972  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x2977  stloc.s  4
0x2979  ldarg.0
0x297a  ldloc.s  4
0x297c  callvirt instance string [mscorlib]System.Object::ToString()
0x2981  stfld    string class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::_uriText
0x2986  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x298b  ldc.i4.s 0x21
0x298d  ldstr    aSandboxclientb_2// "SandboxClientBase.Start: {0}"
0x2992  ldc.i4.1
0x2993  newarr   [mscorlib]System.Object
0x2998  dup
0x2999  ldc.i4.0
0x299a  ldarg.0
0x299b  ldfld    string class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::_uriText
0x29a0  stelem.ref
0x29a1  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x29a6  ldstr    aSdkclientversi// "SdkClientVersion"
0x29ab  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x29b0  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::get_FileVersion()
0x29b5  call     class [System.ServiceModel]System.ServiceModel.Channels.AddressHeader [System.ServiceModel]System.ServiceModel.Channels.AddressHeader::CreateAddressHeader(string, string, object)
0x29ba  stloc.s  5
0x29bc  ldarg.0
0x29bd  call     instance bool class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::get_DestinationOnly()
0x29c2  brtrue.s loc_2A30
0x29c4  ldarg.s  5
0x29c6  brtrue.s loc_29F5
0x29c8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x29cd  ldc.i4.s 0x21
0x29cf  ldstr    aSandboxclientb_3// "SandboxClientBase.Start: no endpoint Id"...
0x29d4  ldc.i4.0
0x29d5  newarr   [mscorlib]System.Object
0x29da  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x29df  ldloc.s  4
0x29e1  ldc.i4.1
0x29e2  newarr   [System.ServiceModel]System.ServiceModel.Channels.AddressHeader
0x29e7  dup
0x29e8  ldc.i4.0
0x29e9  ldloc.s  5
0x29eb  stelem.ref
0x29ec  newobj   instance void [System.ServiceModel]System.ServiceModel.EndpointAddress::.ctor(class [System]System.Uri, class [System.ServiceModel]System.ServiceModel.Channels.AddressHeader[])
0x29f1  stloc.s  6
0x29f3  br.s     loc_2A0B
0x29f5  ldloc.s  4
0x29f7  ldarg.s  5
0x29f9  ldc.i4.1
0x29fa  newarr   [System.ServiceModel]System.ServiceModel.Channels.AddressHeader
0x29ff  dup
0x2a00  ldc.i4.0
0x2a01  ldloc.s  5
0x2a03  stelem.ref
0x2a04  newobj   instance void [System.ServiceModel]System.ServiceModel.EndpointAddress::.ctor(class [System]System.Uri, class [System.ServiceModel]System.ServiceModel.EndpointIdentity, class [System.ServiceModel]System.ServiceModel.Channels.AddressHeader[])
0x2a09  stloc.s  6
0x2a0b  ldarg.0
0x2a0c  ldloc.3
0x2a0d  ldloc.s  6
0x2a0f  callvirt instance var<u1> class [System.ServiceModel]System.ServiceModel.ChannelFactory`1<var<u1>>::CreateChannel(!!T0)
0x2a14  stfld    var<u1> class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::_proxy
0x2a19  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a1e  ldc.i4.s 0x21
0x2a20  ldstr    aSandboxclientb_4// "SandboxClientBase.Start: created WCF ch"...
0x2a25  ldc.i4.0
0x2a26  newarr   [mscorlib]System.Object
0x2a2b  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x2a30  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a35  ldc.i4.s 0x21
0x2a37  ldloc.1
0x2a38  ldftn    instance string class <>c__DisplayClass20_0<var<u1>>::<Start>b__0()
0x2a3e  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x2a43  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, class [mscorlib]System.Func`1<string> traceFunction)
0x2a48  leave.s  loc_2A6A
0x2a4a  stloc.s  7
0x2a4c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2a51  ldc.i4.s 0x21
0x2a53  ldstr    aSandboxclientb_2// "SandboxClientBase.Start: {0}"
0x2a58  ldc.i4.1
0x2a59  newarr   [mscorlib]System.Object
0x2a5e  dup
0x2a5f  ldc.i4.0
0x2a60  ldloc.s  7
0x2a62  stelem.ref
0x2a63  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x2a68  rethrow
0x2a6a  ret
```
