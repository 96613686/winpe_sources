# Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthProviderFactory::Create_0

- ea: `0x2540`
- end: `0x2549`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthProviderFactory::Create_0`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2290`

## pseudocode

```c

```

## disassembly

```asm
0x2540  ldarg.1
0x2541  ldarg.2
0x2542  ldarg.3
0x2543  newobj   instance void Microsoft.Xrm.Async.Bridges.FromCommonAuth.AppKeyOAuthTokenProvider::.ctor(class Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo applicationInfo, string appKey, class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContextFactory contextFactory)
0x2548  ret
```
