# Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::get_DecryptionCertificate

- ea: `0xa2e0`
- end: `0xa30a`
- name: `Microsoft.Crm.Authentication.Claims.IdentityConfigurationProvider::get_DecryptionCertificate`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x149c0`

## callees

- `0xa2e0`
- `0xb070`
- `0xbe80`

## pseudocode

```c

```

## disassembly

```asm
0xa2e0  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Authentication.Claims.ClaimsUtility::get_ServiceCertificate()
0xa2e5  brfalse.s loc_A306
0xa2e7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0xa2ec  stloc.0
0xa2ed  ldloca.s 1
0xa2ef  call     bool Microsoft.Crm.Authentication.Claims.CertificateUtility::TryGetRelyingPartyCertificate([out] class [System]System.Security.Cryptography.X509Certificates.X509Certificate2& certificate)
0xa2f4  brfalse.s loc_A2FA
0xa2f6  ldloc.1
0xa2f7  stloc.2
0xa2f8  leave.s  loc_A308
0xa2fa  leave.s  loc_A306
0xa2fc  ldloc.0
0xa2fd  brfalse.s loc_A305
0xa2ff  ldloc.0
0xa300  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa305  endfinally
0xa306  ldnull
0xa307  ret
0xa308  ldloc.2
0xa309  ret
```
