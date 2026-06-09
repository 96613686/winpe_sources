# Microsoft.Crm.Authentication.Claims.TrustedIssuerRegistry::.ctor

- ea: `0x10bc0`
- end: `0x10c1f`
- name: `Microsoft.Crm.Authentication.Claims.TrustedIssuerRegistry::.ctor`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x149c0`

## callees

- `0x8120`
- `0x81a0`
- `0x8430`
- `0x8450`
- `0x10bc0`

## pseudocode

```c

```

## disassembly

```asm
0x10bc0  ldarg.0
0x10bc1  call     instance void [System.IdentityModel]System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry::.ctor()
0x10bc6  call     class Microsoft.Crm.Authentication.Providers.CertificateProvider Microsoft.Crm.Authentication.Providers.CertificateProvider::get_Instance()
0x10bcb  callvirt instance class Microsoft.Crm.Authentication.Providers.CertificateCollection Microsoft.Crm.Authentication.Providers.CertificateProvider::get_TrustedIssuerCertificates()
0x10bd0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Authentication.Providers.CertificateInformation>::GetEnumerator()
0x10bd5  stloc.0
0x10bd6  br.s     loc_10C0A
0x10bd8  ldloc.0
0x10bd9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Authentication.Providers.CertificateInformation>::get_Current()
0x10bde  stloc.1
0x10bdf  ldarg.0
0x10be0  ldloc.1
0x10be1  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.Crm.Authentication.Providers.CertificateInformation::get_Certificate()
0x10be6  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_Thumbprint()
0x10beb  ldloc.1
0x10bec  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Authentication.Providers.CertificateInformation::get_Properties()
0x10bf1  ldstr    aName// "Name"
0x10bf6  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x10bfb  callvirt instance string [mscorlib]System.Object::ToString()
0x10c00  call     instance void [System.IdentityModel]System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry::AddTrustedIssuer(string, string)
0x10c05  leave.s  loc_10C0A
0x10c07  pop
0x10c08  leave.s  loc_10C0A
0x10c0a  ldloc.0
0x10c0b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10c10  brtrue.s loc_10BD8
0x10c12  leave.s  loc_10C1E
0x10c14  ldloc.0
0x10c15  brfalse.s loc_10C1D
0x10c17  ldloc.0
0x10c18  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10c1d  endfinally
0x10c1e  ret
```
