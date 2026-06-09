# Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::CreateAsync

- ea: `0x29f0`
- end: `0x2a39`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory::CreateAsync`
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
0x29f0  ldloca.s 0
0x29f2  ldarg.0
0x29f3  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderFactory <CreateAsync>d__6::<>4__this
0x29f8  ldloca.s 0
0x29fa  ldarg.1
0x29fb  stfld    string <CreateAsync>d__6::connectionStringKey
0x2a00  ldloca.s 0
0x2a02  ldarg.2
0x2a03  stfld    class [System]System.Uri <CreateAsync>d__6::audienceUri
0x2a08  ldloca.s 0
0x2a0a  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider>::Create()
0x2a0f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> <CreateAsync>d__6::<>t__builder
0x2a14  ldloca.s 0
0x2a16  ldc.i4.m1
0x2a17  stfld    int32 <CreateAsync>d__6::<>1__state
0x2a1c  ldloc.0
0x2a1d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> <CreateAsync>d__6::<>t__builder
0x2a22  stloc.1
0x2a23  ldloca.s 1
0x2a25  ldloca.s 0
0x2a27  call     T0x2B00006D
0x2a2c  ldloca.s 0
0x2a2e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider> <CreateAsync>d__6::<>t__builder
0x2a33  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class Microsoft.Xrm.Async.Bridges.FromCommonAuth.IAuthProvider>::get_Task()
0x2a38  ret
```
