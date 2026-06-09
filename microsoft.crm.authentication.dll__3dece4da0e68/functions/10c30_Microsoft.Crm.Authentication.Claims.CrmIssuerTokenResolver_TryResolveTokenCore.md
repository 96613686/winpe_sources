# Microsoft.Crm.Authentication.Claims.CrmIssuerTokenResolver::TryResolveTokenCore

- ea: `0x10c30`
- end: `0x10cdb`
- name: `Microsoft.Crm.Authentication.Claims.CrmIssuerTokenResolver::TryResolveTokenCore`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x8120`
- `0x81a0`
- `0x8430`
- `0x10c30`

## pseudocode

```c

```

## disassembly

```asm
0x10c30  ldarg.1
0x10c31  ldstr    aKeyidentifierc// "keyIdentifierClause"
0x10c36  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x10c3b  ldarg.2
0x10c3c  ldnull
0x10c3d  stind.ref
0x10c3e  ldarg.1
0x10c3f  isinst   [System.IdentityModel]System.IdentityModel.Tokens.X509RawDataKeyIdentifierClause
0x10c44  stloc.0
0x10c45  ldloc.0
0x10c46  brfalse.s loc_10C5C
0x10c48  ldarg.2
0x10c49  ldloc.0
0x10c4a  callvirt instance unsigned int8[] [System.IdentityModel]System.IdentityModel.Tokens.X509RawDataKeyIdentifierClause::GetX509RawData()
0x10c4f  newobj   instance void [System]System.Security.Cryptography.X509Certificates.X509Certificate2::.ctor(unsigned int8[])
0x10c54  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x10c59  stind.ref
0x10c5a  ldc.i4.1
0x10c5b  ret
0x10c5c  ldarg.1
0x10c5d  isinst   [System.IdentityModel]System.IdentityModel.Tokens.RsaKeyIdentifierClause
0x10c62  stloc.1
0x10c63  ldloc.1
0x10c64  brfalse.s loc_10C75
0x10c66  ldarg.2
0x10c67  ldloc.1
0x10c68  callvirt instance class [mscorlib]System.Security.Cryptography.RSA [System.IdentityModel]System.IdentityModel.Tokens.RsaKeyIdentifierClause::get_Rsa()
0x10c6d  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.RsaSecurityToken::.ctor(class [mscorlib]System.Security.Cryptography.RSA)
0x10c72  stind.ref
0x10c73  ldc.i4.1
0x10c74  ret
0x10c75  ldarg.1
0x10c76  isinst   [System.IdentityModel]System.IdentityModel.Tokens.X509ThumbprintKeyIdentifierClause
0x10c7b  stloc.2
0x10c7c  call     class Microsoft.Crm.Authentication.Providers.CertificateProvider Microsoft.Crm.Authentication.Providers.CertificateProvider::get_Instance()
0x10c81  callvirt instance class Microsoft.Crm.Authentication.Providers.CertificateCollection Microsoft.Crm.Authentication.Providers.CertificateProvider::get_TrustedIssuerCertificates()
0x10c86  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Authentication.Providers.CertificateInformation>::GetEnumerator()
0x10c8b  stloc.3
0x10c8c  br.s     loc_10CB6
0x10c8e  ldloc.3
0x10c8f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Authentication.Providers.CertificateInformation>::get_Current()
0x10c94  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.Crm.Authentication.Providers.CertificateInformation::get_Certificate()
0x10c99  stloc.s  4
0x10c9b  ldloc.2
0x10c9c  brfalse.s loc_10CB6
0x10c9e  ldloc.2
0x10c9f  ldloc.s  4
0x10ca1  callvirt instance bool [System.IdentityModel]System.IdentityModel.Tokens.X509ThumbprintKeyIdentifierClause::Matches(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x10ca6  brfalse.s loc_10CB6
0x10ca8  ldarg.2
0x10ca9  ldloc.s  4
0x10cab  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x10cb0  stind.ref
0x10cb1  ldc.i4.1
0x10cb2  stloc.s  5
0x10cb4  leave.s  loc_10CD8
0x10cb6  ldloc.3
0x10cb7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10cbc  brtrue.s loc_10C8E
0x10cbe  leave.s  loc_10CCA
0x10cc0  ldloc.3
0x10cc1  brfalse.s loc_10CC9
0x10cc3  ldloc.3
0x10cc4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10cc9  endfinally
0x10cca  ldarg.0
0x10ccb  call     instance class [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver [System.IdentityModel]System.IdentityModel.Tokens.IssuerTokenResolver::get_WrappedTokenResolver()
0x10cd0  ldarg.1
0x10cd1  ldarg.2
0x10cd2  callvirt instance bool [System.IdentityModel]System.IdentityModel.Selectors.SecurityTokenResolver::TryResolveToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKeyIdentifierClause, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken&)
0x10cd7  ret
0x10cd8  ldloc.s  5
0x10cda  ret
```
