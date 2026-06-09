# Microsoft.Xrm.Async.Bridges.FromCommonAuth.AppKeyOAuthTokenProvider::AcquireTokenAsync

- ea: `0x22c0`
- end: `0x22d3`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.AppKeyOAuthTokenProvider::AcquireTokenAsync`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2390`
- `0x2900`

## pseudocode

```c

```

## disassembly

```asm
0x22c0  ldarg.1
0x22c1  ldarg.2
0x22c2  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo::get_AppUri()
0x22c7  ldarg.0
0x22c8  ldfld    class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientCredential Microsoft.Xrm.Async.Bridges.FromCommonAuth.AppKeyOAuthTokenProvider::clientCred
0x22cd  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult> Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContext::AcquireTokenAsync(string resource, class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientCredential clientCredential)
0x22d2  ret
```
