# Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::.ctor

- ea: `0x29c0`
- end: `0x29ec`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::.ctor`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x29c0  ldarg.0
0x29c1  call     instance void [mscorlib]System.Object::.ctor()
0x29c6  ldarg.0
0x29c7  ldarg.1
0x29c8  stfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookup Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::secretLookup
0x29cd  ldarg.0
0x29ce  ldarg.2
0x29cf  stfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ICertificateLookup Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::certificateLookup
0x29d4  ldarg.0
0x29d5  ldarg.3
0x29d6  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContextFactory Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::contextFactory
0x29db  ldarg.0
0x29dc  ldarg.s  4
0x29de  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProviderFactory Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::authProviderFactory
0x29e3  ldarg.0
0x29e4  ldarg.s  5
0x29e6  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IConnectionStringConfigParser Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::connectionStringConfigParser
0x29eb  ret
```
