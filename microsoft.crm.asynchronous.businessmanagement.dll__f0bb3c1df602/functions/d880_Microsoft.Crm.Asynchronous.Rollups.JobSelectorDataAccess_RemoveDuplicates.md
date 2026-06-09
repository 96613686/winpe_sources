# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::RemoveDuplicates

- ea: `0xd880`
- end: `0xd8be`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::RemoveDuplicates`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xd280`

## callees

- `0xd880`
- `0xd940`
- `0xdf60`

## pseudocode

```c

```

## disassembly

```asm
0xd880  newobj   instance void Microsoft.Crm.Asynchronous.Rollups.RollupJobComparerForDequeuing::.ctor()
0xd885  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Crm.Asynchronous.Rollups.RollupJob>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0xd88a  stloc.0
0xd88b  ldarg.1
0xd88c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Rollups.RollupJob>::get_Count()
0xd891  ldc.i4.1
0xd892  sub
0xd893  stloc.1
0xd894  br.s     loc_D8B9
0xd896  ldarg.1
0xd897  ldloc.1
0xd898  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Rollups.RollupJob>::get_Item(!!T0)
0xd89d  stloc.2
0xd89e  ldloc.0
0xd89f  ldloc.2
0xd8a0  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<class Microsoft.Crm.Asynchronous.Rollups.RollupJob>::Add(var<u1>)
0xd8a5  brtrue.s loc_D8B5
0xd8a7  ldloc.2
0xd8a8  callvirt instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.RollupJob::Delete()
0xd8ad  pop
0xd8ae  ldarg.1
0xd8af  ldloc.1
0xd8b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Rollups.RollupJob>::RemoveAt(int32)
0xd8b5  ldloc.1
0xd8b6  ldc.i4.1
0xd8b7  sub
0xd8b8  stloc.1
0xd8b9  ldloc.1
0xd8ba  ldc.i4.0
0xd8bb  bge.s    loc_D896
0xd8bd  ret
```
