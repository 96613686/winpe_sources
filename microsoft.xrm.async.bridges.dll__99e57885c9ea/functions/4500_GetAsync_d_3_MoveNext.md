# <GetAsync>d__3::MoveNext

- ea: `0x4500`
- end: `0x45be`
- name: `<GetAsync>d__3::MoveNext`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x2c70`
- `0x4500`

## pseudocode

```c

```

## disassembly

```asm
0x4500  ldarg.0
0x4501  ldfld    int32 <GetAsync>d__3::<>1__state
0x4506  stloc.0
0x4507  ldloc.0
0x4508  brfalse.s loc_455A
0x450a  ldarg.0
0x450b  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderBase <GetAsync>d__3::<>4__this
0x4510  ldarg.0
0x4511  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderBase <GetAsync>d__3::<>4__this
0x4516  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContext Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderBase::authContext
0x451b  ldarg.0
0x451c  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderBase <GetAsync>d__3::<>4__this
0x4521  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderBase::applicationInfo
0x4526  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult> Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderBase::AcquireTokenAsync(class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthenticationContext context, class Microsoft.Xrm.Async.Bridges.FromCommonAuth.ApplicationInfo applicationInfo)
0x452b  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult>::GetAwaiter()
0x4530  stloc.2
0x4531  ldloca.s 2
0x4533  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult>::get_IsCompleted()
0x4538  brtrue.s loc_4576
0x453a  ldarg.0
0x453b  ldc.i4.0
0x453c  dup
0x453d  stloc.0
0x453e  stfld    int32 <GetAsync>d__3::<>1__state
0x4543  ldarg.0
0x4544  ldloc.2
0x4545  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult> <GetAsync>d__3::<>u__1
0x454a  ldarg.0
0x454b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue> <GetAsync>d__3::<>t__builder
0x4550  ldloca.s 2
0x4552  ldarg.0
0x4553  call     T0x2B00008A
0x4558  leave.s  loc_45BD
0x455a  ldarg.0
0x455b  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult> <GetAsync>d__3::<>u__1
0x4560  stloc.2
0x4561  ldarg.0
0x4562  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult> <GetAsync>d__3::<>u__1
0x4567  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult>
0x456d  ldarg.0
0x456e  ldc.i4.m1
0x456f  dup
0x4570  stloc.0
0x4571  stfld    int32 <GetAsync>d__3::<>1__state
0x4576  ldloca.s 2
0x4578  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult>::GetResult()
0x457d  ldloca.s 2
0x457f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult>
0x4585  callvirt instance string [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult::CreateAuthorizationHeader()
0x458a  call     class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue::Parse(string)
0x458f  stloc.1
0x4590  leave.s  loc_45A9
0x4592  stloc.3
0x4593  ldarg.0
0x4594  ldc.i4.s 0xFE
0x4596  stfld    int32 <GetAsync>d__3::<>1__state
0x459b  ldarg.0
0x459c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue> <GetAsync>d__3::<>t__builder
0x45a1  ldloc.3
0x45a2  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue>::SetException(class [mscorlib]System.Exception)
0x45a7  leave.s  loc_45BD
0x45a9  ldarg.0
0x45aa  ldc.i4.s 0xFE
0x45ac  stfld    int32 <GetAsync>d__3::<>1__state
0x45b1  ldarg.0
0x45b2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue> <GetAsync>d__3::<>t__builder
0x45b7  ldloc.1
0x45b8  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue>::SetResult(var<u1>)
0x45bd  ret
```
