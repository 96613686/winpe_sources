# Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextAdapter::AcquireTokenSilentAsync

- ea: `0x2470`
- end: `0x247f`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextAdapter::AcquireTokenSilentAsync`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2470  ldarg.0
0x2471  ldfld    class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextAdapter::context
0x2476  ldarg.1
0x2477  ldarg.2
0x2478  ldarg.3
0x2479  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult> [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::AcquireTokenSilentAsync(string, class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientCredential, class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.UserIdentifier)
0x247e  ret
```
