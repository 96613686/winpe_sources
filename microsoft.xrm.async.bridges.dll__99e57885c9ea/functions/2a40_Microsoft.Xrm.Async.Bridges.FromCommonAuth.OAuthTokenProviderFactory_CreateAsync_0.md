# Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::CreateAsync_0

- ea: `0x2a40`
- end: `0x2a89`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::CreateAsync_0`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2a40  ldloca.s 0
0x2a42  ldarg.0
0x2a43  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory <CreateAsync>d__7::<>4__this
0x2a48  ldloca.s 0
0x2a4a  ldarg.1
0x2a4b  stfld    class [System]System.Uri <CreateAsync>d__7::connectionStringUri
0x2a50  ldloca.s 0
0x2a52  ldarg.2
0x2a53  stfld    class [System]System.Uri <CreateAsync>d__7::audienceUri
0x2a58  ldloca.s 0
0x2a5a  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider>::Create()
0x2a5f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> <CreateAsync>d__7::<>t__builder
0x2a64  ldloca.s 0
0x2a66  ldc.i4.m1
0x2a67  stfld    int32 <CreateAsync>d__7::<>1__state
0x2a6c  ldloc.0
0x2a6d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> <CreateAsync>d__7::<>t__builder
0x2a72  stloc.1
0x2a73  ldloca.s 1
0x2a75  ldloca.s 0
0x2a77  call     T0x2B00006E
0x2a7c  ldloca.s 0
0x2a7e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> <CreateAsync>d__7::<>t__builder
0x2a83  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider>::get_Task()
0x2a88  ret
```
