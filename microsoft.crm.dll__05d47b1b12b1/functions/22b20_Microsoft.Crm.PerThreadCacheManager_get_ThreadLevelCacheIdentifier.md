# Microsoft.Crm.PerThreadCacheManager::get_ThreadLevelCacheIdentifier

- ea: `0x22b20`
- end: `0x22b76`
- name: `Microsoft.Crm.PerThreadCacheManager::get_ThreadLevelCacheIdentifier`
- size: `86`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x225a0`
- `0x226a0`
- `0x226f0`
- `0x22810`
- `0x22850`
- `0x22890`
- `0x22960`
- `0x229e0`

## callees

- `0x22b80`

## string_xrefs

- `0x22b26`: `A valid OrganizationId must be set in the PerThreadCacheManager`
- `0x22b38`: `ThreadLevelCache`

## pseudocode

```c

```

## disassembly

```asm
0x22b20  ldarg.0
0x22b21  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.PerThreadCacheManager::get_OrganizationId()
0x22b26  ldstr    aAValidOrganiza// "A valid OrganizationId must be set in t"...
0x22b2b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x22b30  ldc.i4.4
0x22b31  newarr   [mscorlib]System.Object
0x22b36  dup
0x22b37  ldc.i4.0
0x22b38  ldstr    aThreadlevelcac// "ThreadLevelCache"
0x22b3d  stelem.ref
0x22b3e  dup
0x22b3f  ldc.i4.1
0x22b40  ldarg.0
0x22b41  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.PerThreadCacheManager::get_OrganizationId()
0x22b46  box      [mscorlib]System.Guid
0x22b4b  stelem.ref
0x22b4c  dup
0x22b4d  ldc.i4.2
0x22b4e  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x22b53  callvirt instance int32 [mscorlib]System.AppDomain::get_Id()
0x22b58  box      [mscorlib]System.Int32
0x22b5d  stelem.ref
0x22b5e  dup
0x22b5f  ldc.i4.3
0x22b60  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x22b65  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x22b6a  box      [mscorlib]System.Int32
0x22b6f  stelem.ref
0x22b70  call     string [mscorlib]System.String::Concat(object[])
0x22b75  ret
```
