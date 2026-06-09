# Microsoft.Crm.Authentication.OpenId.JsonWebKey::GetSigningCertificates

- ea: `0x6d90`
- end: `0x6de9`
- name: `Microsoft.Crm.Authentication.OpenId.JsonWebKey::GetSigningCertificates`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6d70`

## callees

- `0x6d50`
- `0x6d70`
- `0x6d90`
- `0x10950`
- `0x10970`
- `0x10980`
- `0x109a0`

## pseudocode

```c

```

## disassembly

```asm
0x6d90  ldarg.0
0x6d91  newobj   instance void Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection::.ctor()
0x6d96  stfld    class Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection Microsoft.Crm.Authentication.OpenId.JsonWebKey::_trustedIssuers
0x6d9b  ldarg.0
0x6d9c  call     instance string[] Microsoft.Crm.Authentication.OpenId.JsonWebKey::get_X5C()
0x6da1  stloc.0
0x6da2  ldc.i4.0
0x6da3  stloc.1
0x6da4  br.s     loc_6DE2
0x6da6  ldloc.0
0x6da7  ldloc.1
0x6da8  ldelem.ref
0x6da9  stloc.2
0x6daa  ldloc.2
0x6dab  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x6db0  newobj   instance void [System]System.Security.Cryptography.X509Certificates.X509Certificate2::.ctor(unsigned int8[])
0x6db5  stloc.3
0x6db6  ldarg.0
0x6db7  call     instance class Microsoft.Crm.Authentication.Claims.TrustedIssuerCollection Microsoft.Crm.Authentication.OpenId.JsonWebKey::get_TrustedIssuers()
0x6dbc  newobj   instance void Microsoft.Crm.Authentication.Claims.TrustedIssuer::.ctor()
0x6dc1  dup
0x6dc2  ldloc.3
0x6dc3  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName [System]System.Security.Cryptography.X509Certificates.X509Certificate2::get_SubjectName()
0x6dc8  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X500DistinguishedName::get_Name()
0x6dcd  callvirt instance void Microsoft.Crm.Authentication.Claims.TrustedIssuer::set_Name(string value)
0x6dd2  dup
0x6dd3  ldloc.2
0x6dd4  callvirt instance void Microsoft.Crm.Authentication.Claims.TrustedIssuer::set_Certificate(string value)
0x6dd9  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Authentication.Claims.TrustedIssuer>::Add(var<u1>)
0x6dde  ldloc.1
0x6ddf  ldc.i4.1
0x6de0  add
0x6de1  stloc.1
0x6de2  ldloc.1
0x6de3  ldloc.0
0x6de4  ldlen
0x6de5  conv.i4
0x6de6  blt.s    loc_6DA6
0x6de8  ret
```
