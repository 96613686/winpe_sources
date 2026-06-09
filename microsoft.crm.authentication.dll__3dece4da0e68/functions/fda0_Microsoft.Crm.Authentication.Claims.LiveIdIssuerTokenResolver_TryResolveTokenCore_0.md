# Microsoft.Crm.Authentication.Claims.LiveIdIssuerTokenResolver::TryResolveTokenCore_0

- ea: `0xfda0`
- end: `0xfe74`
- name: `Microsoft.Crm.Authentication.Claims.LiveIdIssuerTokenResolver::TryResolveTokenCore_0`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x8120`
- `0x81a0`
- `0x8430`
- `0xfda0`

## pseudocode

```c

```

## disassembly

```asm
0xfda0  ldarg.1
0xfda1  brtrue.s loc_FDAE
0xfda3  ldstr    aKeyidentifierc// "keyIdentifierClause"
0xfda8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfdad  throw
0xfdae  ldarg.2
0xfdaf  ldnull
0xfdb0  stind.ref
0xfdb1  call     class Microsoft.Crm.Authentication.Providers.CertificateProvider Microsoft.Crm.Authentication.Providers.CertificateProvider::get_Instance()
0xfdb6  callvirt instance class Microsoft.Crm.Authentication.Providers.CertificateCollection Microsoft.Crm.Authentication.Providers.CertificateProvider::get_TrustedIssuerCertificates()
0xfdbb  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Authentication.Providers.CertificateInformation>::GetEnumerator()
0xfdc0  stloc.0
0xfdc1  br       loc_FE58
0xfdc6  ldloc.0
0xfdc7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Authentication.Providers.CertificateInformation>::get_Current()
0xfdcc  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.Crm.Authentication.Providers.CertificateInformation::get_Certificate()
0xfdd1  stloc.1
0xfdd2  ldarg.1
0xfdd3  isinst   [System.IdentityModel]System.IdentityModel.Tokens.X509ThumbprintKeyIdentifierClause
0xfdd8  stloc.2
0xfdd9  ldloc.2
0xfdda  brfalse.s loc_FDF2
0xfddc  ldloc.2
0xfddd  ldloc.1
0xfdde  callvirt instance bool [System.IdentityModel]System.IdentityModel.Tokens.X509ThumbprintKeyIdentifierClause::Matches(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0xfde3  brfalse.s loc_FDF2
0xfde5  ldarg.2
0xfde6  ldloc.1
0xfde7  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0xfdec  stind.ref
0xfded  ldc.i4.1
0xfdee  stloc.s  6
0xfdf0  leave.s  loc_FE71
0xfdf2  ldarg.1
0xfdf3  isinst   [System.IdentityModel]System.IdentityModel.Tokens.X509IssuerSerialKeyIdentifierClause
0xfdf8  stloc.3
0xfdf9  ldloc.3
0xfdfa  brfalse.s loc_FE12
0xfdfc  ldloc.3
0xfdfd  ldloc.1
0xfdfe  callvirt instance bool [System.IdentityModel]System.IdentityModel.Tokens.X509IssuerSerialKeyIdentifierClause::Matches(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0xfe03  brfalse.s loc_FE12
0xfe05  ldarg.2
0xfe06  ldloc.1
0xfe07  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0xfe0c  stind.ref
0xfe0d  ldc.i4.1
0xfe0e  stloc.s  6
0xfe10  leave.s  loc_FE71
0xfe12  ldarg.1
0xfe13  isinst   [System.IdentityModel]System.IdentityModel.Tokens.X509SubjectKeyIdentifierClause
0xfe18  stloc.s  4
0xfe1a  ldloc.s  4
0xfe1c  brfalse.s loc_FE35
0xfe1e  ldloc.s  4
0xfe20  ldloc.1
0xfe21  callvirt instance bool [System.IdentityModel]System.IdentityModel.Tokens.X509SubjectKeyIdentifierClause::Matches(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0xfe26  brfalse.s loc_FE35
0xfe28  ldarg.2
0xfe29  ldloc.1
0xfe2a  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0xfe2f  stind.ref
0xfe30  ldc.i4.1
0xfe31  stloc.s  6
0xfe33  leave.s  loc_FE71
0xfe35  ldarg.1
0xfe36  isinst   [System.IdentityModel]System.IdentityModel.Tokens.X509RawDataKeyIdentifierClause
0xfe3b  stloc.s  5
0xfe3d  ldloc.s  5
0xfe3f  brfalse.s loc_FE58
0xfe41  ldloc.s  5
0xfe43  ldloc.1
0xfe44  callvirt instance bool [System.IdentityModel]System.IdentityModel.Tokens.X509RawDataKeyIdentifierClause::Matches(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0xfe49  brfalse.s loc_FE58
0xfe4b  ldarg.2
0xfe4c  ldloc.1
0xfe4d  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0xfe52  stind.ref
0xfe53  ldc.i4.1
0xfe54  stloc.s  6
0xfe56  leave.s  loc_FE71
0xfe58  ldloc.0
0xfe59  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xfe5e  brtrue   loc_FDC6
0xfe63  leave.s  loc_FE6F
0xfe65  ldloc.0
0xfe66  brfalse.s loc_FE6E
0xfe68  ldloc.0
0xfe69  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xfe6e  endfinally
0xfe6f  ldc.i4.0
0xfe70  ret
0xfe71  ldloc.s  6
0xfe73  ret
```
