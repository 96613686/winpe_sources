# Microsoft.Xrm.Async.Bridges.FromCommonAuth.CertificateOAuthTokenProvider::AcquireTokenAsync

- ea: `0x25a0`
- end: `0x25b3`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.CertificateOAuthTokenProvider::AcquireTokenAsync`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x2390`
- `0x28f0`

## pseudocode

```c

```

## disassembly

```asm
0x25a0  ldarg.1
0x25a1  ldarg.2
0x25a2  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo::get_AppUri()
0x25a7  ldarg.0
0x25a8  ldfld    class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate Microsoft.Xrm.Async.Bridges.FromCommonAuth.CertificateOAuthTokenProvider::certCred
0x25ad  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult> Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContext::AcquireTokenAsync(string resource, class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate clientCertificate)
0x25b2  ret
```
