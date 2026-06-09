# Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::PostCommitTransactionCacheRemoveHandler

- ea: `0x4cda0`
- end: `0x4ce73`
- name: `Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::PostCommitTransactionCacheRemoveHandler`
- size: `211`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4cc30`
- `0x4cda0`
- `0x4d010`
- `0x4d040`
- `0x4e460`

## string_xrefs

- `0x4cda8`: `PostCommitTransactionCacheRemoveHandler called in PerThreadCacheMetadataCacheManager for Org={0}`
- `0x4ce02`: `Not An Error: PostCommitTransactionCacheRemoveHandler Called. The PerThreadCacheMetadataCache should be cleared`
- `0x4ce50`: `MetadataCache`

## pseudocode

```c

```

## disassembly

```asm
0x4cda0  ldarg.0
0x4cda1  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::get_OrganizationId()
0x4cda6  ldc.i4.s 0x19
0x4cda8  ldstr    aPostcommittran// "PostCommitTransactionCacheRemoveHandler"...
0x4cdad  ldc.i4.1
0x4cdae  newarr   [mscorlib]System.Object
0x4cdb3  dup
0x4cdb4  ldc.i4.0
0x4cdb5  ldarg.0
0x4cdb6  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::get_OrganizationId()
0x4cdbb  box      [mscorlib]System.Guid
0x4cdc0  stelem.ref
0x4cdc1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4cdc6  ldarg.2
0x4cdc7  isinst   [Microsoft.Crm.Core]Microsoft.Crm.PostCommitTransactionEventArgs
0x4cdcc  stloc.0
0x4cdcd  ldloc.0
0x4cdce  brfalse  loc_4CE72
0x4cdd3  ldloc.0
0x4cdd4  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.PostCommitTransactionEventArgs::get_Parameter()
0x4cdd9  brfalse  loc_4CE72
0x4cdde  ldloc.0
0x4cddf  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.PostCommitTransactionEventArgs::get_Parameter()
0x4cde4  castclass class [System.Core]System.Collections.Generic.HashSet`1<string>
0x4cde9  stloc.1
0x4cdea  ldloc.1
0x4cdeb  brfalse  loc_4CE72
0x4cdf0  ldloc.1
0x4cdf1  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<string>::get_Count()
0x4cdf6  ldc.i4.0
0x4cdf7  ble.s    loc_4CE72
0x4cdf9  ldnull
0x4cdfa  ldarg.0
0x4cdfb  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::get_OrganizationId()
0x4ce00  ldc.i4.s 0x19
0x4ce02  ldstr    aNotAnErrorPost// "Not An Error: PostCommitTransactionCach"...
0x4ce07  ldc.i4.0
0x4ce08  newarr   [mscorlib]System.Object
0x4ce0d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4ce12  ldloc.1
0x4ce13  ldarg.0
0x4ce14  call     instance string Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::get_OrganizationIdAsString()
0x4ce19  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x4ce1e  brfalse.s loc_4CE4F
0x4ce20  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContextFactory::get_Current()
0x4ce25  ldarg.0
0x4ce26  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::get_OrganizationId()
0x4ce2b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory::GetOrganizationContext(valuetype [mscorlib]System.Guid)
0x4ce30  stloc.2
0x4ce31  ldarg.0
0x4ce32  ldloc.2
0x4ce33  ldc.i4.1
0x4ce34  call     instance void Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, bool forceRemoveCache)
0x4ce39  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContextFactory::get_Current()
0x4ce3e  ldarg.0
0x4ce3f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::get_OrganizationId()
0x4ce44  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContextFactory::GetOrganizationContext(valuetype [mscorlib]System.Guid)
0x4ce49  call     void Microsoft.Crm.Metadata.MetadataCache::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4ce4e  ret
0x4ce4f  ldloc.1
0x4ce50  ldstr    aMetadatacache// "MetadataCache"
0x4ce55  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x4ce5a  brfalse.s loc_4CE72
0x4ce5c  ldarg.0
0x4ce5d  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Metadata.DummyOrganizationContext::.ctor()
0x4ce62  ldc.i4.1
0x4ce63  call     instance void Microsoft.Crm.Metadata.PerThreadMetadataCacheManager::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, bool forceRemoveCache)
0x4ce68  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Metadata.DummyOrganizationContext::.ctor()
0x4ce6d  call     void Microsoft.Crm.Metadata.MetadataCache::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4ce72  ret
```
