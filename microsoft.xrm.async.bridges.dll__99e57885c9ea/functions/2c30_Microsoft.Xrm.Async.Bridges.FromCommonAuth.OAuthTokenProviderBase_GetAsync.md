# Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderBase::GetAsync

- ea: `0x2c30`
- end: `0x2c69`
- name: `Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderBase::GetAsync`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2c30  ldloca.s 0
0x2c32  ldarg.0
0x2c33  stfld    class Microsoft.Xrm.Async.Bridges.FromCommonAuth.OAuthTokenProviderBase <GetAsync>d__3::<>4__this
0x2c38  ldloca.s 0
0x2c3a  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue>::Create()
0x2c3f  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue> <GetAsync>d__3::<>t__builder
0x2c44  ldloca.s 0
0x2c46  ldc.i4.m1
0x2c47  stfld    int32 <GetAsync>d__3::<>1__state
0x2c4c  ldloc.0
0x2c4d  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue> <GetAsync>d__3::<>t__builder
0x2c52  stloc.1
0x2c53  ldloca.s 1
0x2c55  ldloca.s 0
0x2c57  call     T0x2B000074
0x2c5c  ldloca.s 0
0x2c5e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue> <GetAsync>d__3::<>t__builder
0x2c63  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [System.Net.Http]System.Net.Http.Headers.AuthenticationHeaderValue>::get_Task()
0x2c68  ret
```
