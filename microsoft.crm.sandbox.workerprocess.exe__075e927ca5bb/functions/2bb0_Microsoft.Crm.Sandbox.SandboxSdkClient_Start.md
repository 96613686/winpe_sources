# Microsoft.Crm.Sandbox.SandboxSdkClient::Start

- ea: `0x2bb0`
- end: `0x2d0b`
- name: `Microsoft.Crm.Sandbox.SandboxSdkClient::Start`
- size: `347`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1ec0`
- `0x2220`

## callees

- `0x2bb0`

## pseudocode

```c

```

## disassembly

```asm
0x2bb0  newobj   instance void [System]System.UriBuilder::.ctor()
0x2bb5  stloc.0
0x2bb6  ldarg.1
0x2bb7  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Port()
0x2bbc  ldc.i4.0
0x2bbd  ble.s    loc_2BD2
0x2bbf  ldloc.0
0x2bc0  ldc.i4.5
0x2bc1  ldstr    a127001// "127.0.0.1"
0x2bc6  call     T0x2B000007
0x2bcb  callvirt instance void [System]System.UriBuilder::set_Host(string)
0x2bd0  br.s     loc_2BF1
0x2bd2  ldarg.1
0x2bd3  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_MachineName()
0x2bd8  ldnull
0x2bd9  cgt.un
0x2bdb  ldstr    aCallinfoMachin// "callInfo.MachineName is null"
0x2be0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x2be5  ldloc.0
0x2be6  ldarg.1
0x2be7  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_MachineName()
0x2bec  callvirt instance void [System]System.UriBuilder::set_Host(string)
0x2bf1  ldnull
0x2bf2  stloc.2
0x2bf3  ldnull
0x2bf4  stloc.3
0x2bf5  ldc.i4.s 0x16
0x2bf7  ldc.i4.0
0x2bf8  call     T0x2B000009
0x2bfd  stloc.s  4
0x2bff  ldarg.1
0x2c00  callvirt instance bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_UseDrawBridgeIsolation()
0x2c05  brtrue.s loc_2C19
0x2c07  ldloc.s  4
0x2c09  ldc.i4.0
0x2c0a  ble.s    loc_2C80
0x2c0c  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x2c11  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x2c16  ldc.i4.1
0x2c17  bne.un.s loc_2C80
0x2c19  ldc.i4.0
0x2c1a  stloc.1
0x2c1b  newobj   instance void [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::.ctor()
0x2c20  stloc.3
0x2c21  ldloc.3
0x2c22  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_ServiceCertificate()
0x2c27  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential::get_Authentication()
0x2c2c  ldc.i4.0
0x2c2d  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication::set_CertificateValidationMode(valuetype [System.IdentityModel]System.ServiceModel.Security.X509CertificateValidationMode)
0x2c32  ldloc.3
0x2c33  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential [System.ServiceModel]System.ServiceModel.Description.ClientCredentials::get_ServiceCertificate()
0x2c38  callvirt instance class [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication [System.ServiceModel]System.ServiceModel.Security.X509CertificateRecipientClientCredential::get_Authentication()
0x2c3d  ldc.i4.0
0x2c3e  callvirt instance void [System.ServiceModel]System.ServiceModel.Security.X509ServiceCertificateAuthentication::set_RevocationMode(valuetype [System]System.Security.Cryptography.X509Certificates.X509RevocationMode)
0x2c43  ldarg.1
0x2c44  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ServiceCertificateDNSName()
0x2c49  call     class [System.ServiceModel]System.ServiceModel.EndpointIdentity [System.ServiceModel]System.ServiceModel.EndpointIdentity::CreateDnsIdentity(string)
0x2c4e  stloc.2
0x2c4f  ldarg.1
0x2c50  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Port()
0x2c55  brtrue   loc_2CEA
0x2c5a  ldloc.0
0x2c5b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c60  ldstr    aAnonymousclien// "AnonymousClientCrmSandboxSdkListener-{0"...
0x2c65  ldc.i4.1
0x2c66  newarr   [mscorlib]System.Object
0x2c6b  dup
0x2c6c  ldc.i4.0
0x2c6d  ldarg.1
0x2c6e  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ProcessName()
0x2c73  stelem.ref
0x2c74  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2c79  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x2c7e  br.s     loc_2CEA
0x2c80  ldc.i4.1
0x2c81  stloc.1
0x2c82  ldarg.1
0x2c83  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_FullMachineName()
0x2c88  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2c8d  brtrue.s loc_2C97
0x2c8f  ldarg.1
0x2c90  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_FullMachineName()
0x2c95  br.s     loc_2C9D
0x2c97  ldarg.1
0x2c98  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_MachineName()
0x2c9d  ldarg.1
0x2c9e  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ServiceClassForServerPrincipalName()
0x2ca3  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::GetSpnIdentityString(string, string)
0x2ca8  stloc.s  5
0x2caa  ldloc.s  5
0x2cac  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2cb1  brtrue.s loc_2CBC
0x2cb3  ldloc.s  5
0x2cb5  call     class [System.ServiceModel]System.ServiceModel.EndpointIdentity [System.ServiceModel]System.ServiceModel.EndpointIdentity::CreateSpnIdentity(string)
0x2cba  br.s     loc_2CBD
0x2cbc  ldnull
0x2cbd  stloc.2
0x2cbe  ldarg.1
0x2cbf  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Port()
0x2cc4  brtrue.s loc_2CEA
0x2cc6  ldloc.0
0x2cc7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ccc  ldstr    aCrmsandboxsdkl// "CrmSandboxSdkListener-{0}"
0x2cd1  ldc.i4.1
0x2cd2  newarr   [mscorlib]System.Object
0x2cd7  dup
0x2cd8  ldc.i4.0
0x2cd9  ldarg.1
0x2cda  callvirt instance string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ProcessName()
0x2cdf  stelem.ref
0x2ce0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2ce5  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x2cea  ldarg.1
0x2ceb  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Port()
0x2cf0  ldc.i4.0
0x2cf1  ble.s    loc_2CFF
0x2cf3  ldloc.0
0x2cf4  ldarg.1
0x2cf5  callvirt instance int32 [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Port()
0x2cfa  callvirt instance void [System]System.UriBuilder::set_Port(int32)
0x2cff  ldarg.0
0x2d00  ldloc.0
0x2d01  ldloc.1
0x2d02  ldloc.3
0x2d03  ldc.i4.8
0x2d04  ldloc.2
0x2d05  call     instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::Start(class [System]System.UriBuilder, valuetype [System.ServiceModel]System.ServiceModel.TcpClientCredentialType, class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials, valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix, class [System.ServiceModel]System.ServiceModel.EndpointIdentity)
0x2d0a  ret
```
