# Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::CreateCertificateOAuthTokenProvider

- ea: `0x2a90`
- end: `0x2aa4`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::CreateCertificateOAuthTokenProvider`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2ab0`

## callees

- `0x28c0`

## pseudocode

```c

```

## disassembly

```asm
0x2a90  ldarg.0
0x2a91  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProviderFactory Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::authProviderFactory
0x2a96  ldarg.1
0x2a97  ldarg.2
0x2a98  ldarg.0
0x2a99  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContextFactory Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::contextFactory
0x2a9e  callvirt instance class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProviderFactory::Create(class Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo applicationInfo, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 certificate, class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContextFactory contextFactory)
0x2aa3  ret
```
