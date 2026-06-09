# Microsoft.Crm.PerThreadCacheManager::.ctor

- ea: `0x22530`
- end: `0x2256c`
- name: `Microsoft.Crm.PerThreadCacheManager::.ctor`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x22b80`

## string_xrefs

- `0x22549`: `Creating per thread cache for thread={0}`

## pseudocode

```c

```

## disassembly

```asm
0x22530  ldarg.0
0x22531  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>>::.ctor()
0x22536  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<object, class [mscorlib]System.Collections.Generic.List`1<string>>> Microsoft.Crm.PerThreadCacheManager::_cacheEntriesMarkedForRemoval
0x2253b  ldarg.0
0x2253c  call     instance void [mscorlib]System.Object::.ctor()
0x22541  ldarg.0
0x22542  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.PerThreadCacheManager::get_OrganizationId()
0x22547  ldc.i4.s 0x1A
0x22549  ldstr    aCreatingPerThr// "Creating per thread cache for thread={0"...
0x2254e  ldc.i4.1
0x2254f  newarr   [mscorlib]System.Object
0x22554  dup
0x22555  ldc.i4.0
0x22556  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x2255b  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x22560  box      [mscorlib]System.Int32
0x22565  stelem.ref
0x22566  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2256b  ret
```
