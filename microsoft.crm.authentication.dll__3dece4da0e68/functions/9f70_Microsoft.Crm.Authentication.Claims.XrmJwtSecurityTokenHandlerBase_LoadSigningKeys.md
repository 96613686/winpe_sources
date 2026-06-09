# Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::LoadSigningKeys

- ea: `0x9f70`
- end: `0x9fc5`
- name: `Microsoft.Crm.Authentication.Claims.XrmJwtSecurityTokenHandlerBase::LoadSigningKeys`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xa1e0`

## callees

- `0x8120`
- `0x81a0`
- `0x8430`
- `0x9f70`

## pseudocode

```c

```

## disassembly

```asm
0x9f70  call     class Microsoft.Crm.Authentication.Providers.CertificateProvider Microsoft.Crm.Authentication.Providers.CertificateProvider::get_Instance()
0x9f75  callvirt instance class Microsoft.Crm.Authentication.Providers.CertificateCollection Microsoft.Crm.Authentication.Providers.CertificateProvider::get_TrustedIssuerCertificates()
0x9f7a  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Authentication.Providers.CertificateInformation>::get_Count()
0x9f7f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken>::.ctor(int32)
0x9f84  stloc.0
0x9f85  call     class Microsoft.Crm.Authentication.Providers.CertificateProvider Microsoft.Crm.Authentication.Providers.CertificateProvider::get_Instance()
0x9f8a  callvirt instance class Microsoft.Crm.Authentication.Providers.CertificateCollection Microsoft.Crm.Authentication.Providers.CertificateProvider::get_TrustedIssuerCertificates()
0x9f8f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Authentication.Providers.CertificateInformation>::GetEnumerator()
0x9f94  stloc.1
0x9f95  br.s     loc_9FAF
0x9f97  ldloc.1
0x9f98  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Authentication.Providers.CertificateInformation>::get_Current()
0x9f9d  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.Crm.Authentication.Providers.CertificateInformation::get_Certificate()
0x9fa2  stloc.2
0x9fa3  ldloc.0
0x9fa4  ldloc.2
0x9fa5  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x9faa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken>::Add(var<u1>)
0x9faf  ldloc.1
0x9fb0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9fb5  brtrue.s loc_9F97
0x9fb7  leave.s  loc_9FC3
0x9fb9  ldloc.1
0x9fba  brfalse.s loc_9FC2
0x9fbc  ldloc.1
0x9fbd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9fc2  endfinally
0x9fc3  ldloc.0
0x9fc4  ret
```
