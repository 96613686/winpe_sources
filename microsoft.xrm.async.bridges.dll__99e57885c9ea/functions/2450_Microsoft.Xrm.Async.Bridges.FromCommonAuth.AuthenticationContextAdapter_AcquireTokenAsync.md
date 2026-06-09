# Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextAdapter::AcquireTokenAsync

- ea: `0x2450`
- end: `0x245e`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextAdapter::AcquireTokenAsync`
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
0x2450  ldarg.0
0x2451  ldfld    class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext Microsoft.Xrm.Async.Bridges.FromCommonAuth.AuthenticationContextAdapter::context
0x2456  ldarg.1
0x2457  ldarg.2
0x2458  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult> [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::AcquireTokenAsync(string, class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate)
0x245d  ret
```
