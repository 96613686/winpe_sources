# <GetAccessToken>d__9::MoveNext

- ea: `0x3900`
- end: `0x39be`
- name: `<GetAccessToken>d__9::MoveNext`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x3900`

## pseudocode

```c

```

## disassembly

```asm
0x3900  ldarg.0
0x3901  ldfld    int32 <GetAccessToken>d__9::<>1__state
0x3906  stloc.0
0x3907  ldloc.0
0x3908  brfalse.s loc_395F
0x390a  ldarg.0
0x390b  ldfld    string <GetAccessToken>d__9::authority
0x3910  call     class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.TokenCache [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.TokenCache::get_DefaultShared()
0x3915  newobj   instance void [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::.ctor(string, class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.TokenCache)
0x391a  ldarg.0
0x391b  ldfld    string <GetAccessToken>d__9::resource
0x3920  ldarg.0
0x3921  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter <GetAccessToken>d__9::<>4__this
0x3926  ldfld    class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate Microsoft.Xrm.Async.Bridges.FromCommonProvidersKeyVault.KeyVaultAdapter::assertionCertificate
0x392b  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult> [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext::AcquireTokenAsync(string, class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.ClientAssertionCertificate)
0x3930  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult>::GetAwaiter()
0x3935  stloc.2
0x3936  ldloca.s 2
0x3938  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult>::get_IsCompleted()
0x393d  brtrue.s loc_397B
0x393f  ldarg.0
0x3940  ldc.i4.0
0x3941  dup
0x3942  stloc.0
0x3943  stfld    int32 <GetAccessToken>d__9::<>1__state
0x3948  ldarg.0
0x3949  ldloc.2
0x394a  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult> <GetAccessToken>d__9::<>u__1
0x394f  ldarg.0
0x3950  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetAccessToken>d__9::<>t__builder
0x3955  ldloca.s 2
0x3957  ldarg.0
0x3958  call     T0x2B000080
0x395d  leave.s  loc_39BD
0x395f  ldarg.0
0x3960  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult> <GetAccessToken>d__9::<>u__1
0x3965  stloc.2
0x3966  ldarg.0
0x3967  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult> <GetAccessToken>d__9::<>u__1
0x396c  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult>
0x3972  ldarg.0
0x3973  ldc.i4.m1
0x3974  dup
0x3975  stloc.0
0x3976  stfld    int32 <GetAccessToken>d__9::<>1__state
0x397b  ldloca.s 2
0x397d  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult>::GetResult()
0x3982  ldloca.s 2
0x3984  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult>
0x398a  callvirt instance string [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult::get_AccessToken()
0x398f  stloc.1
0x3990  leave.s  loc_39A9
0x3992  stloc.3
0x3993  ldarg.0
0x3994  ldc.i4.s 0xFE
0x3996  stfld    int32 <GetAccessToken>d__9::<>1__state
0x399b  ldarg.0
0x399c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetAccessToken>d__9::<>t__builder
0x39a1  ldloc.3
0x39a2  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetException(class [mscorlib]System.Exception)
0x39a7  leave.s  loc_39BD
0x39a9  ldarg.0
0x39aa  ldc.i4.s 0xFE
0x39ac  stfld    int32 <GetAccessToken>d__9::<>1__state
0x39b1  ldarg.0
0x39b2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetAccessToken>d__9::<>t__builder
0x39b7  ldloc.1
0x39b8  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetResult(var<u1>)
0x39bd  ret
```
