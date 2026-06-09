# Microsoft.Crm.Authentication.Claims.CrmSessionSecurityTokenHandler::get_DefaultTransforms

- ea: `0x9c40`
- end: `0x9c8f`
- name: `Microsoft.Crm.Authentication.Claims.CrmSessionSecurityTokenHandler::get_DefaultTransforms`
- size: `79`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x99d0`
- `0x9c90`

## callees

- `0x9c40`
- `0xb070`
- `0xbe80`

## pseudocode

```c

```

## disassembly

```asm
0x9c40  ldsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.CookieTransform> Microsoft.Crm.Authentication.Claims.CrmSessionSecurityTokenHandler::_transforms
0x9c45  brtrue.s loc_9C89
0x9c47  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_ServiceCertificate()
0x9c4c  brfalse.s loc_9C89
0x9c4e  ldloca.s 0
0x9c50  call     bool Microsoft.Crm.Authentication.Claims.CertificateUtility::TryGetRelyingPartyCertificate([out] class [System]System.Security.Cryptography.X509Certificates.X509Certificate2& certificate)
0x9c55  brfalse.s loc_9C89
0x9c57  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.CookieTransform>::.ctor()
0x9c5c  dup
0x9c5d  newobj   instance void [System.IdentityModel]System.IdentityModel.DeflateCookieTransform::.ctor()
0x9c62  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.CookieTransform>::Add(var<u1>)
0x9c67  dup
0x9c68  ldloc.0
0x9c69  newobj   instance void [System.IdentityModel]System.IdentityModel.RsaEncryptionCookieTransform::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x9c6e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.CookieTransform>::Add(var<u1>)
0x9c73  dup
0x9c74  ldloc.0
0x9c75  newobj   instance void [System.IdentityModel]System.IdentityModel.RsaSignatureCookieTransform::.ctor(class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x9c7a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.CookieTransform>::Add(var<u1>)
0x9c7f  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [System.IdentityModel]System.IdentityModel.CookieTransform>::AsReadOnly()
0x9c84  stsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.CookieTransform> Microsoft.Crm.Authentication.Claims.CrmSessionSecurityTokenHandler::_transforms
0x9c89  ldsfld   class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.CookieTransform> Microsoft.Crm.Authentication.Claims.CrmSessionSecurityTokenHandler::_transforms
0x9c8e  ret
```
