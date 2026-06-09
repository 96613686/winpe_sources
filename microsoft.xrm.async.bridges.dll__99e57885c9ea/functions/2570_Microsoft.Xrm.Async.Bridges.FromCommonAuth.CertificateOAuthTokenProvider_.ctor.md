# Microsoft.Xrm.Async.Bridges.FromCommonAuth.CertificateOAuthTokenProvider::.ctor

- ea: `0x2570`
- end: `0x259c`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.CertificateOAuthTokenProvider::.ctor`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2530`

## callees

- `0x2370`
- `0x2be0`

## pseudocode

```c

```

## disassembly

```asm
0x2570  ldarg.0
0x2571  ldarg.1
0x2572  ldarg.3
0x2573  call     instance void Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderBase::.ctor(class Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo applicationInfo, class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContextFactory contextFactory)
0x2578  ldarg.2
0x2579  ldstr    aCertificate// "certificate"
0x257e  call     T0x2B000028
0x2583  call     T0x2B000029
0x2588  pop
0x2589  ldarg.0
0x258a  ldarg.1
0x258b  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo::get_ClientId()
0x2590  ldarg.2
0x2591  newobj   instance void [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate::.ctor(string, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2)
0x2596  stfld    class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate Microsoft.Xrm.Async.Bridges.FromCommonAuth.CertificateOAuthTokenProvider::certCred
0x259b  ret
```
