# Microsoft.Crm.Sandbox.SandboxSdkListener::StartListenerWithAnonymousClient

- ea: `0x4f70`
- end: `0x5028`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::StartListenerWithAnonymousClient`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4e80`

## callees

- `0x4f70`

## string_xrefs

- `0x4fd9`: `Service Bus Issuer Certificate`
- `0x4feb`: `SandboxSdkListener.StartListenerWithAnonymousClient: Retrieved ServiceBusIssuer Certificate is null.`

## pseudocode

```c

```

## disassembly

```asm
0x4f70  newobj   instance void [System]System.UriBuilder::.ctor()
0x4f75  stloc.0
0x4f76  ldloc.0
0x4f77  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4f7c  ldstr    aAnonymousclien// "AnonymousClientCrmSandboxSdkListener-{0"...
0x4f81  ldc.i4.1
0x4f82  newarr   [mscorlib]System.Object
0x4f87  dup
0x4f88  ldc.i4.0
0x4f89  ldsfld   string Microsoft.Crm.Sandbox.SandboxSdkListener::_processName
0x4f8e  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxSdkListener::_processId
0x4f93  ldsfld   int32 Microsoft.Crm.Sandbox.SandboxSdkListener::_appDomainId
0x4f98  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::GetListenerEndpointSuffix(string, int32, int32)
0x4f9d  stelem.ref
0x4f9e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4fa3  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x4fa8  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxListener`2<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener, class Microsoft.Crm.Sandbox.SandboxSdkListener>::NewListener()
0x4fad  stsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener Microsoft.Crm.Sandbox.SandboxSdkListener::_anonymousClientListener
0x4fb2  newobj   instance void [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials::.ctor()
0x4fb7  stloc.1
0x4fb8  ldsfld   class [mscorlib]System.Lazy`1<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2> Microsoft.Crm.Sandbox.SandboxSdkListener::ListenerCertificate
0x4fbd  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Value()
0x4fc2  stloc.2
0x4fc3  ldloc.2
0x4fc4  brtrue.s loc_4FFC
0x4fc6  ldloc.2
0x4fc7  brtrue.s loc_4FE4
0x4fc9  ldc.i4.2
0x4fca  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x4fcf  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x4fd4  ldc.i4.2
0x4fd5  and
0x4fd6  bne.un.s loc_4FE4
0x4fd8  ldloc.2
0x4fd9  ldstr    aServiceBusIssu// "Service Bus Issuer Certificate"
0x4fde  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4fe3  ret
0x4fe4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4fe9  ldc.i4.s 0x26
0x4feb  ldstr    aSandboxsdklist_16// "SandboxSdkListener.StartListenerWithAno"...
0x4ff0  ldc.i4.0
0x4ff1  newarr   [mscorlib]System.Object
0x4ff6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4ffb  ret
0x4ffc  ldloc.1
0x4ffd  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientServiceCredential [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials::get_ServiceCertificate()
0x5002  ldloc.2
0x5003  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientServiceCredential::set_Certificate(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x5008  ldsfld   class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener Microsoft.Crm.Sandbox.SandboxSdkListener::_anonymousClientListener
0x500d  ldloc.0
0x500e  ldc.i4.0
0x500f  ldloc.1
0x5010  ldc.i4.5
0x5011  ldc.i4   0x40004F02
0x5016  conv.i8
0x5017  ldc.i4   0xC0004F12
0x501c  conv.u8
0x501d  ldstr    aSdkListener// "SDK Listener"
0x5022  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxListener::StartListening(class [System]System.UriBuilder, valuetype [System.ServiceModel]System.ServiceModel.TcpClientCredentialType, class [System.ServiceModel]System.ServiceModel.Description.ServiceCredentials, valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix, int64, int64, string)
0x5027  ret
```
