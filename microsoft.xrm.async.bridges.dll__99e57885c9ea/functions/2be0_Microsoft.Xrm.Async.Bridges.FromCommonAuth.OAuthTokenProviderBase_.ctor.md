# Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderBase::.ctor

- ea: `0x2be0`
- end: `0x2c22`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderBase::.ctor`
- size: `66`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2290`
- `0x2570`

## callees

- `0x2380`
- `0x2930`

## pseudocode

```c

```

## disassembly

```asm
0x2be0  ldarg.0
0x2be1  call     instance void [mscorlib]System.Object::.ctor()
0x2be6  ldarg.1
0x2be7  ldstr    aApplicationinf// "applicationInfo"
0x2bec  call     T0x2B000070
0x2bf1  call     T0x2B000071
0x2bf6  pop
0x2bf7  ldarg.2
0x2bf8  ldstr    aContextfactory// "contextFactory"
0x2bfd  call     T0x2B000072
0x2c02  call     T0x2B000073
0x2c07  pop
0x2c08  ldarg.0
0x2c09  ldarg.1
0x2c0a  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderBase::applicationInfo
0x2c0f  ldarg.0
0x2c10  ldarg.2
0x2c11  ldarg.1
0x2c12  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo::get_AuthorityUrl()
0x2c17  callvirt instance class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContext Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContextFactory::Create(string authority)
0x2c1c  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContext Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderBase::authContext
0x2c21  ret
```
