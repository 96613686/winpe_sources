# Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthProviderFactory::Create

- ea: `0x2530`
- end: `0x2539`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthProviderFactory::Create`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2570`

## pseudocode

```c

```

## disassembly

```asm
0x2530  ldarg.1
0x2531  ldarg.2
0x2532  ldarg.3
0x2533  newobj   instance void Microsoft.Xrm.Async.Bridges.FromCommonAuth.CertificateOAuthTokenProvider::.ctor(class Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo applicationInfo, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 certificate, class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContextFactory contextFactory)
0x2538  ret
```
