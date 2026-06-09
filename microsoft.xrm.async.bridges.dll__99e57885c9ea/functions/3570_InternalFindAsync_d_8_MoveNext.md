# <InternalFindAsync>d__8::MoveNext

- ea: `0x3570`
- end: `0x36d7`
- name: `<InternalFindAsync>d__8::MoveNext`
- size: `359`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1080`
- `0x1210`
- `0x1250`
- `0x1560`
- `0x1590`
- `0x3570`

## string_xrefs

- `0x358b`: `ExpiringSecretCache`
- `0x3670`: `ExpiringSecretCache`

## pseudocode

```c

```

## disassembly

```asm
0x3570  ldarg.0
0x3571  ldfld    int32 <InternalFindAsync>d__8::<>1__state
0x3576  stloc.0
0x3577  ldloc.0
0x3578  brfalse.s loc_3595
0x357a  ldarg.0
0x357b  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache <InternalFindAsync>d__8::<>4__this
0x3580  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::events
0x3585  ldarg.0
0x3586  ldfld    string <InternalFindAsync>d__8::key
0x358b  ldstr    aExpiringsecret// "ExpiringSecretCache"
0x3590  callvirt instance void Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents::OnBeginFind(string key, string callerType)
0x3595  nop
0x3596  ldloc.0
0x3597  brfalse.s loc_35FE
0x3599  ldarg.0
0x359a  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache <InternalFindAsync>d__8::<>4__this
0x359f  ldarg.0
0x35a0  ldfld    string <InternalFindAsync>d__8::key
0x35a5  ldarg.0
0x35a6  ldfld    valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions <InternalFindAsync>d__8::options
0x35ab  callvirt instance string Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::GetCachedSecret(string key, valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions options)
0x35b0  stloc.2
0x35b1  ldloc.2
0x35b2  brfalse.s loc_35BB
0x35b4  ldloc.2
0x35b5  stloc.1
0x35b6  leave    loc_36C2
0x35bb  ldarg.0
0x35bc  ldfld    class [mscorlib]System.Func`2<valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions, class [mscorlib]System.Threading.Tasks.Task`1<string>> <InternalFindAsync>d__8::innerFindFunc
0x35c1  ldarg.0
0x35c2  ldfld    valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions <InternalFindAsync>d__8::options
0x35c7  callvirt instance var<u1> class [mscorlib]System.Func`2<valuetype Microsoft.Xrm.Async.Bridges.FromCommon.RetrievalOptions, class [mscorlib]System.Threading.Tasks.Task`1<string>>::Invoke(void)
0x35cc  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<string>::GetAwaiter()
0x35d1  stloc.3
0x35d2  ldloca.s 3
0x35d4  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::get_IsCompleted()
0x35d9  brtrue.s loc_361A
0x35db  ldarg.0
0x35dc  ldc.i4.0
0x35dd  dup
0x35de  stloc.0
0x35df  stfld    int32 <InternalFindAsync>d__8::<>1__state
0x35e4  ldarg.0
0x35e5  ldloc.3
0x35e6  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <InternalFindAsync>d__8::<>u__1
0x35eb  ldarg.0
0x35ec  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <InternalFindAsync>d__8::<>t__builder
0x35f1  ldloca.s 3
0x35f3  ldarg.0
0x35f4  call     T0x2B00007E
0x35f9  leave    loc_36D6
0x35fe  ldarg.0
0x35ff  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <InternalFindAsync>d__8::<>u__1
0x3604  stloc.3
0x3605  ldarg.0
0x3606  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string> <InternalFindAsync>d__8::<>u__1
0x360b  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x3611  ldarg.0
0x3612  ldc.i4.m1
0x3613  dup
0x3614  stloc.0
0x3615  stfld    int32 <InternalFindAsync>d__8::<>1__state
0x361a  ldloca.s 3
0x361c  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>::GetResult()
0x3621  ldloca.s 3
0x3623  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<string>
0x3629  stloc.2
0x362a  ldloc.2
0x362b  brtrue.s loc_3634
0x362d  ldnull
0x362e  stloc.1
0x362f  leave    loc_36C2
0x3634  ldarg.0
0x3635  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache <InternalFindAsync>d__8::<>4__this
0x363a  ldarg.0
0x363b  ldfld    string <InternalFindAsync>d__8::key
0x3640  ldloc.2
0x3641  callvirt instance void Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::CacheSecret(string key, string secret)
0x3646  ldloc.2
0x3647  stloc.1
0x3648  leave.s  loc_36C2
0x364a  isinst   [mscorlib]System.Exception
0x364f  dup
0x3650  brtrue.s loc_3656
0x3652  pop
0x3653  ldc.i4.0
0x3654  br.s     loc_367F
0x3656  stloc.s  4
0x3658  ldarg.0
0x3659  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache <InternalFindAsync>d__8::<>4__this
0x365e  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::events
0x3663  ldarg.0
0x3664  ldfld    string <InternalFindAsync>d__8::key
0x3669  ldloc.s  4
0x366b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3670  ldstr    aExpiringsecret// "ExpiringSecretCache"
0x3675  ldloc.s  4
0x3677  callvirt instance bool Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents::OnFailedFind(string key, string error, string callerType, class [mscorlib]System.Exception exception)
0x367c  ldc.i4.0
0x367d  cgt.un
0x367f  endfilter
0x3681  pop
0x3682  ldarg.0
0x3683  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache <InternalFindAsync>d__8::<>4__this
0x3688  ldfld    class Microsoft.Xrm.Async.Bridges.FromCommon.ISecretLookupEvents Microsoft.Xrm.Async.Bridges.FromCommon.ExpiringSecretCache::events
0x368d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3692  callvirt instance string [mscorlib]System.Type::get_FullName()
0x3697  ldstr    aOnfailedfind// ".OnFailedFind"
0x369c  call     string [mscorlib]System.String::Concat(string, string)
0x36a1  ldloc.s  4
0x36a3  newobj   instance void Microsoft.Xrm.Async.Bridges.FromCommon.ExceptionFilterContractViolationException::.ctor(string filterMemberFullName, class [mscorlib]System.Exception innerException)
0x36a8  throw
0x36a9  stloc.s  5
0x36ab  ldarg.0
0x36ac  ldc.i4.s 0xFE
0x36ae  stfld    int32 <InternalFindAsync>d__8::<>1__state
0x36b3  ldarg.0
0x36b4  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <InternalFindAsync>d__8::<>t__builder
0x36b9  ldloc.s  5
0x36bb  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetException(class [mscorlib]System.Exception)
0x36c0  leave.s  loc_36D6
0x36c2  ldarg.0
0x36c3  ldc.i4.s 0xFE
0x36c5  stfld    int32 <InternalFindAsync>d__8::<>1__state
0x36ca  ldarg.0
0x36cb  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <InternalFindAsync>d__8::<>t__builder
0x36d0  ldloc.1
0x36d1  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetResult(var<u1>)
0x36d6  ret
```
