# Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::InternalFindAsync

- ea: `0x11b0`
- end: `0x1201`
- name: `Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::InternalFindAsync`
- size: `81`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x10f0`
- `0x1160`

## pseudocode

```c

```

## disassembly

```asm
0x11b0  ldloca.s 0
0x11b2  ldarg.0
0x11b3  stfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache <InternalFindAsync>d__8::<>4__this
0x11b8  ldloca.s 0
0x11ba  ldarg.1
0x11bb  stfld    string <InternalFindAsync>d__8::key
0x11c0  ldloca.s 0
0x11c2  ldarg.2
0x11c3  stfld    valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions <InternalFindAsync>d__8::options
0x11c8  ldloca.s 0
0x11ca  ldarg.3
0x11cb  stfld    class [mscorlib]System.Func`2<valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions, class [mscorlib]System.Threading.Tasks.Task`1<string>> <InternalFindAsync>d__8::innerFindFunc
0x11d0  ldloca.s 0
0x11d2  call     valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::Create()
0x11d7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <InternalFindAsync>d__8::<>t__builder
0x11dc  ldloca.s 0
0x11de  ldc.i4.m1
0x11df  stfld    int32 <InternalFindAsync>d__8::<>1__state
0x11e4  ldloc.0
0x11e5  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <InternalFindAsync>d__8::<>t__builder
0x11ea  stloc.1
0x11eb  ldloca.s 1
0x11ed  ldloca.s 0
0x11ef  call     T0x2B000025
0x11f4  ldloca.s 0
0x11f6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <InternalFindAsync>d__8::<>t__builder
0x11fb  call     instance class [mscorlib]System.Threading.Tasks.Task`1<var<u1>> valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::get_Task()
0x1200  ret
```
