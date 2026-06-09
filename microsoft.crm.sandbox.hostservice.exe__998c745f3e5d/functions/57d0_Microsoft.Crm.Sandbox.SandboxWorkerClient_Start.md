# Microsoft.Crm.Sandbox.SandboxWorkerClient::Start

- ea: `0x57d0`
- end: `0x58a9`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerClient::Start`
- size: `217`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x57d0`
- `0xa0f0`
- `0xa350`

## callees

- `0x5790`
- `0x57a0`
- `0x57c0`
- `0x57d0`
- `0x5930`

## string_xrefs

- `0x586f`: `SandboxWorkerClient.Start:Thread[{0:d4}]: Spent {1} ms in StartWorkerClient to successfully start a workerclient`

## pseudocode

```c

```

## disassembly

```asm
0x57d0  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x57d5  stloc.0
0x57d6  ldarg.0
0x57d7  ldc.i4.1
0x57d8  stfld    valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxStatus Microsoft.Crm.Sandbox.SandboxWorkerClient::_workerStatus
0x57dd  ldarg.1
0x57de  newobj   instance void [System]System.UriBuilder::.ctor(class [System]System.Uri)
0x57e3  stloc.1
0x57e4  newobj   instance void [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::.ctor()
0x57e9  stloc.2
0x57ea  ldloc.2
0x57eb  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_ClientCertificate()
0x57f0  ldsfld   class [mscorlib]System.Lazy`1<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2> Microsoft.Crm.Sandbox.SandboxWorkerClient::_sandboxHostCertificate
0x57f5  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Value()
0x57fa  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.X509CertificateInitiatorClientCredential::set_Certificate(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x57ff  ldloc.2
0x5800  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_ServiceCertificate()
0x5805  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential::get_Authentication()
0x580a  ldc.i4.0
0x580b  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication::set_CertificateValidationMode(valuetype [System.IdentityModel]System.ServiceModel.Security.X509CertificateValidationMode)
0x5810  ldloc.2
0x5811  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_ServiceCertificate()
0x5816  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential::get_Authentication()
0x581b  ldc.i4.0
0x581c  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication::set_RevocationMode(valuetype [System]System.Security.Cryptography.X509Certificates.X509RevocationMode)
0x5821  ldsfld   class [mscorlib]System.Lazy`1<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2> Microsoft.Crm.Sandbox.SandboxWorkerClient::_workerProcessCertificate
0x5826  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [System]System.Security.Cryptography.X509Certificates.X509Certificate2>::get_Value()
0x582b  call     class [System.ServiceModel]System.ServiceModel.EndpointIdentity [System.ServiceModel]System.ServiceModel.EndpointIdentity::CreateX509CertificateIdentity(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x5830  stloc.3
0x5831  ldarg.0
0x5832  ldloc.1
0x5833  ldc.i4.2
0x5834  ldloc.2
0x5835  ldc.i4.6
0x5836  ldloc.3
0x5837  call     instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxWorker>::Start(class [System]System.UriBuilder, valuetype [System.ServiceModel]System.ServiceModel.TcpClientCredentialType, class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials, valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix, class [System.ServiceModel]System.ServiceModel.EndpointIdentity)
0x583c  ldarg.2
0x583d  brfalse.s loc_5857
0x583f  ldarg.0
0x5840  newobj   instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::.ctor()
0x5845  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_PingClient(class Microsoft.Crm.Sandbox.SandboxWorkerClient value)
0x584a  ldarg.0
0x584b  call     instance class Microsoft.Crm.Sandbox.SandboxWorkerClient Microsoft.Crm.Sandbox.SandboxWorkerClient::get_PingClient()
0x5850  ldarg.1
0x5851  ldc.i4.0
0x5852  callvirt instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::Start(class [System]System.Uri workerAddress, bool executeClient)
0x5857  ldarg.0
0x5858  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x585d  call     instance void Microsoft.Crm.Sandbox.SandboxWorkerClient::set_LastCall(valuetype [mscorlib]System.DateTime value)
0x5862  ldloc.0
0x5863  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x5868  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x586d  ldc.i4.s 0x21
0x586f  ldstr    aSandboxworkerc// "SandboxWorkerClient.Start:Thread[{0:d4}"...
0x5874  ldc.i4.2
0x5875  newarr   [mscorlib]System.Object
0x587a  dup
0x587b  ldc.i4.0
0x587c  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x5881  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x5886  box      [mscorlib]System.Int32
0x588b  stelem.ref
0x588c  dup
0x588d  ldc.i4.1
0x588e  ldloc.0
0x588f  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x5894  stloc.s  4
0x5896  ldloca.s 4
0x5898  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x589d  box      [mscorlib]System.Double
0x58a2  stelem.ref
0x58a3  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x58a8  ret
```
