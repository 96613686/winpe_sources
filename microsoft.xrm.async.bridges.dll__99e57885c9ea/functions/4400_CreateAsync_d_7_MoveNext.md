# <CreateAsync>d__7::MoveNext

- ea: `0x4400`
- end: `0x44d3`
- name: `<CreateAsync>d__7::MoveNext`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1540`
- `0x2ab0`
- `0x4400`

## pseudocode

```c

```

## disassembly

```asm
0x4400  ldarg.0
0x4401  ldfld    int32 <CreateAsync>d__7::<>1__state
0x4406  stloc.0
0x4407  ldloc.0
0x4408  brfalse.s loc_4459
0x440a  ldarg.0
0x440b  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory <CreateAsync>d__7::<>4__this
0x4410  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookup Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::secretLookup
0x4415  ldarg.0
0x4416  ldfld    class [System]System.Uri <CreateAsync>d__7::connectionStringUri
0x441b  ldloca.s 4
0x441d  initobj  Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions
0x4423  ldloc.s  4
0x4425  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookup::FindAsync(class [System]System.Uri secretUri, [opt] valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions options)
0x442a  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x442f  stloc.3
0x4430  ldloca.s 3
0x4432  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x4437  brtrue.s loc_4475
0x4439  ldarg.0
0x443a  ldc.i4.0
0x443b  dup
0x443c  stloc.0
0x443d  stfld    int32 <CreateAsync>d__7::<>1__state
0x4442  ldarg.0
0x4443  ldloc.3
0x4444  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <CreateAsync>d__7::<>u__1
0x4449  ldarg.0
0x444a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> <CreateAsync>d__7::<>t__builder
0x444f  ldloca.s 3
0x4451  ldarg.0
0x4452  call     T0x2B000089
0x4457  leave.s  loc_44D2
0x4459  ldarg.0
0x445a  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <CreateAsync>d__7::<>u__1
0x445f  stloc.3
0x4460  ldarg.0
0x4461  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <CreateAsync>d__7::<>u__1
0x4466  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x446c  ldarg.0
0x446d  ldc.i4.m1
0x446e  dup
0x446f  stloc.0
0x4470  stfld    int32 <CreateAsync>d__7::<>1__state
0x4475  ldloca.s 3
0x4477  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x447c  ldloca.s 3
0x447e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x4484  stloc.2
0x4485  ldarg.0
0x4486  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory <CreateAsync>d__7::<>4__this
0x448b  ldloc.2
0x448c  ldarg.0
0x448d  ldfld    class [System]System.Uri <CreateAsync>d__7::connectionStringUri
0x4492  callvirt instance string [mscorlib]System.Object::ToString()
0x4497  ldarg.0
0x4498  ldfld    class [System]System.Uri <CreateAsync>d__7::audienceUri
0x449d  callvirt instance class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::CreateFromConnectionString(string connectionString, string connectionStringIdentifier, [opt] class [System]System.Uri audienceUri)
0x44a2  stloc.1
0x44a3  leave.s  loc_44BE
0x44a5  stloc.s  5
0x44a7  ldarg.0
0x44a8  ldc.i4.s 0xFE
0x44aa  stfld    int32 <CreateAsync>d__7::<>1__state
0x44af  ldarg.0
0x44b0  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> <CreateAsync>d__7::<>t__builder
0x44b5  ldloc.s  5
0x44b7  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider>::SetException(class [mscorlib]System.Exception)
0x44bc  leave.s  loc_44D2
0x44be  ldarg.0
0x44bf  ldc.i4.s 0xFE
0x44c1  stfld    int32 <CreateAsync>d__7::<>1__state
0x44c6  ldarg.0
0x44c7  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> <CreateAsync>d__7::<>t__builder
0x44cc  ldloc.1
0x44cd  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider>::SetResult(var<u1>)
0x44d2  ret
```
