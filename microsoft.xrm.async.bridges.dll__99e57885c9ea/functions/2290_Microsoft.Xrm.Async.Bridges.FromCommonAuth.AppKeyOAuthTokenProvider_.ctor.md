# Microsoft.Xrm.Async.Bridges.FromCommonAuth.AppKeyOAuthTokenProvider::.ctor

- ea: `0x2290`
- end: `0x22bc`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.AppKeyOAuthTokenProvider::.ctor`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2540`

## callees

- `0xab0`
- `0x2370`
- `0x2be0`

## pseudocode

```c

```

## disassembly

```asm
0x2290  ldarg.0
0x2291  ldarg.1
0x2292  ldarg.3
0x2293  call     instance void Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderBase::.ctor(class Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo applicationInfo, class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContextFactory contextFactory)
0x2298  ldarg.2
0x2299  ldstr    aAppkey_0// "appKey"
0x229e  call     T0x2B000024
0x22a3  call     class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.Args::IsNotNullOrEmpty(class Microsoft.Xrm.Async.Bridges.FromCommon.ArgumentAssertion`1<string> arg)
0x22a8  pop
0x22a9  ldarg.0
0x22aa  ldarg.1
0x22ab  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo::get_ClientId()
0x22b0  ldarg.2
0x22b1  newobj   instance void [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientCredential::.ctor(string, string)
0x22b6  stfld    class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientCredential Microsoft.Xrm.Async.Bridges.FromCommonAuth.AppKeyOAuthTokenProvider::clientCred
0x22bb  ret
```
