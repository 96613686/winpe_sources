# Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::AddStandardCacheEntryToRemovalList

- ea: `0x4cf40`
- end: `0x4cf9a`
- name: `Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::AddStandardCacheEntryToRemovalList`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x4cb30`

## callees

- `0x4cf40`
- `0x4d010`
- `0x4d040`

## string_xrefs

- `0x4cf4a`: `MetadataCache`
- `0x4cf73`: `Added Metadata Cache:{0} to removal list in PerThreadMetadataCacheManager for Thread:{1}`

## pseudocode

```c

```

## disassembly

```asm
0x4cf40  ldarg.0
0x4cf41  call     instance string Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::get_OrganizationIdAsString()
0x4cf46  stloc.0
0x4cf47  ldarg.1
0x4cf48  brfalse.s loc_4CF50
0x4cf4a  ldstr    aMetadatacache// "MetadataCache"
0x4cf4f  stloc.0
0x4cf50  ldarg.0
0x4cf51  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::_cacheEntriesMarkedForRemoval
0x4cf56  ldloc.0
0x4cf57  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x4cf5c  brtrue.s loc_4CF6B
0x4cf5e  ldarg.0
0x4cf5f  ldfld    class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::_cacheEntriesMarkedForRemoval
0x4cf64  ldloc.0
0x4cf65  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x4cf6a  pop
0x4cf6b  ldarg.0
0x4cf6c  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::get_OrganizationId()
0x4cf71  ldc.i4.s 0x19
0x4cf73  ldstr    aAddedMetadataC// "Added Metadata Cache:{0} to removal lis"...
0x4cf78  ldc.i4.2
0x4cf79  newarr   [mscorlib]System.Object
0x4cf7e  dup
0x4cf7f  ldc.i4.0
0x4cf80  ldloc.0
0x4cf81  stelem.ref
0x4cf82  dup
0x4cf83  ldc.i4.1
0x4cf84  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x4cf89  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x4cf8e  box      [mscorlib]System.Int32
0x4cf93  stelem.ref
0x4cf94  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4cf99  ret
```
