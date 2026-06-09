# Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextAdapter::AcquireTokenAsync_0

- ea: `0x2460`
- end: `0x246e`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextAdapter::AcquireTokenAsync_0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2460  ldarg.0
0x2461  ldfld    class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextAdapter::context
0x2466  ldarg.1
0x2467  ldarg.2
0x2468  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult> [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::AcquireTokenAsync(string, class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientCredential)
0x246d  ret
```
