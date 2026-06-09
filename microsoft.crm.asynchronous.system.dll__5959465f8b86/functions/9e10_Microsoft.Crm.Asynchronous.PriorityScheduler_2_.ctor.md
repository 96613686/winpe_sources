# Microsoft.Crm.Asynchronous.PriorityScheduler`2::.ctor

- ea: `0x9e10`
- end: `0x9e90`
- name: `Microsoft.Crm.Asynchronous.PriorityScheduler`2::.ctor`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x9e4f`: `comparer`

## pseudocode

```c

```

## disassembly

```asm
0x9e10  ldarg.0
0x9e11  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<var<u1>>::.ctor()
0x9e16  stfld    class [System.Core]System.Collections.Generic.HashSet`1<var<u1>> class Microsoft.Crm.Asynchronous.PriorityScheduler`2<var<u1>, !!T0>::_currentlyExecuting
0x9e1b  ldarg.0
0x9e1c  newobj   instance void [mscorlib]System.Object::.ctor()
0x9e21  stfld    object class Microsoft.Crm.Asynchronous.PriorityScheduler`2<var<u1>, !!T0>::_syncObject
0x9e26  ldarg.0
0x9e27  call     instance void [mscorlib]System.Object::.ctor()
0x9e2c  ldarg.1
0x9e2d  ldstr    aId// "id"
0x9e32  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x9e37  ldarg.2
0x9e38  ldstr    aMaxdegreeofpar// "maxDegreeOfParallelism"
0x9e3d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNotPositive(int32, string)
0x9e42  ldarg.3
0x9e43  ldstr    aKeymapper// "keyMapper"
0x9e48  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9e4d  ldarg.s  4
0x9e4f  ldstr    aComparer// "comparer"
0x9e54  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9e59  ldarg.s  5
0x9e5b  ldstr    aAsyncactiontoc// "asyncActionToCall"
0x9e60  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9e65  ldarg.0
0x9e66  ldarg.1
0x9e67  call     instance void class Microsoft.Crm.Asynchronous.PriorityScheduler`2<var<u1>, !!T0>::set_Id(string)
0x9e6c  ldarg.0
0x9e6d  ldarg.2
0x9e6e  call     instance void class Microsoft.Crm.Asynchronous.PriorityScheduler`2<var<u1>, !!T0>::set_MaxDegreeOfParallelism(int32)
0x9e73  ldarg.0
0x9e74  ldarg.s  5
0x9e76  stfld    class [mscorlib]System.Action`1<var<u1>> class Microsoft.Crm.Asynchronous.PriorityScheduler`2<var<u1>, !!T0>::_asyncActionToCall
0x9e7b  ldarg.0
0x9e7c  ldarg.3
0x9e7d  stfld    class [mscorlib]System.Func`2<var<u1>, void> class Microsoft.Crm.Asynchronous.PriorityScheduler`2<var<u1>, !!T0>::_keyMapper
0x9e82  ldarg.0
0x9e83  ldarg.s  4
0x9e85  newobj   instance void class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Collections.KeyedPriorityQueue`2<var<u1>, !!T0>::.ctor(class [mscorlib]System.Collections.Generic.IComparer`1<var<u1>>)
0x9e8a  stfld    class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Collections.KeyedPriorityQueue`2<var<u1>, !!T0> class Microsoft.Crm.Asynchronous.PriorityScheduler`2<var<u1>, !!T0>::_itemsToProcess
0x9e8f  ret
```
