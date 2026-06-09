# Microsoft.Crm.Asynchronous.MultiOrgQueue::TryInitializeOrganizationQueue

- ea: `0xb920`
- end: `0xb961`
- name: `Microsoft.Crm.Asynchronous.MultiOrgQueue::TryInitializeOrganizationQueue`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xb690`
- `0xb8c0`

## callees

- `0xb570`
- `0xb920`
- `0xd0a0`

## string_xrefs

- `0xb93e`: `OrgMaxThreadCount`

## pseudocode

```c

```

## disassembly

```asm
0xb920  ldarg.0
0xb921  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class Microsoft.Crm.Asynchronous.Operations.IThreadPoolOperation>> Microsoft.Crm.Asynchronous.MultiOrgQueue::multiOrgQueue
0xb926  ldarg.1
0xb927  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class Microsoft.Crm.Asynchronous.Operations.IThreadPoolOperation>::.ctor()
0xb92c  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Concurrent.ConcurrentQueue`1<class Microsoft.Crm.Asynchronous.Operations.IThreadPoolOperation>>::TryAdd(var<u1>, !!T0)
0xb931  brfalse.s loc_B95F
0xb933  ldarg.0
0xb934  call     instance bool Microsoft.Crm.Asynchronous.MultiOrgQueue::get_OrgParallelExecutionThrottleEnabled()
0xb939  brtrue.s loc_B93D
0xb93b  ldc.i4.1
0xb93c  ret
0xb93d  ldarg.1
0xb93e  ldstr    aOrgmaxthreadco// "OrgMaxThreadCount"
0xb943  ldc.i4.s 0x14
0xb945  call     int32 Microsoft.Crm.Asynchronous.ServerConfiguration::GetOrganizationSettingOrDefault(valuetype [mscorlib]System.Guid orgId, string settingName, int32 defaultValue)
0xb94a  stloc.0
0xb94b  ldarg.0
0xb94c  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim> Microsoft.Crm.Asynchronous.MultiOrgQueue::orgThreadCountThrottler
0xb951  ldarg.1
0xb952  ldloc.0
0xb953  ldloc.0
0xb954  newobj   instance void [mscorlib]System.Threading.SemaphoreSlim::.ctor(int32, int32)
0xb959  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Threading.SemaphoreSlim>::TryAdd(var<u1>, !!T0)
0xb95e  ret
0xb95f  ldc.i4.0
0xb960  ret
```
