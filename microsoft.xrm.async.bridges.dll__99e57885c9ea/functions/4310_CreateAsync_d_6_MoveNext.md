# <CreateAsync>d__6::MoveNext

- ea: `0x4310`
- end: `0x43de`
- name: `<CreateAsync>d__6::MoveNext`
- size: `206`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1520`
- `0x2ab0`
- `0x4310`

## pseudocode

```c

```

## disassembly

```asm
0x4310  ldarg.0
0x4311  ldfld    int32 <CreateAsync>d__6::<>1__state
0x4316  stloc.0
0x4317  ldloc.0
0x4318  brfalse.s loc_4369
0x431a  ldarg.0
0x431b  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory <CreateAsync>d__6::<>4__this
0x4320  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookup Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::secretLookup
0x4325  ldarg.0
0x4326  ldfld    string <CreateAsync>d__6::connectionStringKey
0x432b  ldloca.s 4
0x432d  initobj  Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions
0x4333  ldloc.s  4
0x4335  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<string> Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookup::FindAsync(string key, [opt] valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions options)
0x433a  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x433f  stloc.3
0x4340  ldloca.s 3
0x4342  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x4347  brtrue.s loc_4385
0x4349  ldarg.0
0x434a  ldc.i4.0
0x434b  dup
0x434c  stloc.0
0x434d  stfld    int32 <CreateAsync>d__6::<>1__state
0x4352  ldarg.0
0x4353  ldloc.3
0x4354  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <CreateAsync>d__6::<>u__1
0x4359  ldarg.0
0x435a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> <CreateAsync>d__6::<>t__builder
0x435f  ldloca.s 3
0x4361  ldarg.0
0x4362  call     T0x2B000088
0x4367  leave.s  loc_43DD
0x4369  ldarg.0
0x436a  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <CreateAsync>d__6::<>u__1
0x436f  stloc.3
0x4370  ldarg.0
0x4371  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <CreateAsync>d__6::<>u__1
0x4376  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x437c  ldarg.0
0x437d  ldc.i4.m1
0x437e  dup
0x437f  stloc.0
0x4380  stfld    int32 <CreateAsync>d__6::<>1__state
0x4385  ldloca.s 3
0x4387  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x438c  ldloca.s 3
0x438e  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x4394  stloc.2
0x4395  ldarg.0
0x4396  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory <CreateAsync>d__6::<>4__this
0x439b  ldloc.2
0x439c  ldarg.0
0x439d  ldfld    string <CreateAsync>d__6::connectionStringKey
0x43a2  ldarg.0
0x43a3  ldfld    class [System]System.Uri <CreateAsync>d__6::audienceUri
0x43a8  callvirt instance class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::CreateFromConnectionString(string connectionString, string connectionStringIdentifier, [opt] class [System]System.Uri audienceUri)
0x43ad  stloc.1
0x43ae  leave.s  loc_43C9
0x43b0  stloc.s  5
0x43b2  ldarg.0
0x43b3  ldc.i4.s 0xFE
0x43b5  stfld    int32 <CreateAsync>d__6::<>1__state
0x43ba  ldarg.0
0x43bb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> <CreateAsync>d__6::<>t__builder
0x43c0  ldloc.s  5
0x43c2  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider>::SetException(class [mscorlib]System.Exception)
0x43c7  leave.s  loc_43DD
0x43c9  ldarg.0
0x43ca  ldc.i4.s 0xFE
0x43cc  stfld    int32 <CreateAsync>d__6::<>1__state
0x43d1  ldarg.0
0x43d2  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> <CreateAsync>d__6::<>t__builder
0x43d7  ldloc.1
0x43d8  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider>::SetResult(var<u1>)
0x43dd  ret
```
