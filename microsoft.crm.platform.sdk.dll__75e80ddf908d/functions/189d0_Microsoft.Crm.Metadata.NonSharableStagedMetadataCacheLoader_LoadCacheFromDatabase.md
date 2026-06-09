# Microsoft.Crm.Metadata.NonSharableStagedMetadataCacheLoader::LoadCacheFromDatabase

- ea: `0x189d0`
- end: `0x18a52`
- name: `Microsoft.Crm.Metadata.NonSharableStagedMetadataCacheLoader::LoadCacheFromDatabase`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0xfd00`
- `0x189d0`
- `0x4e460`
- `0x4f250`
- `0x50cf0`
- `0x50d10`
- `0x50d20`
- `0x51730`
- `0x79850`

## string_xrefs

- `0x189ef`: `Standard cache must be a LockFreeMetadataContainer for PerThreadMetadataCache`
- `0x18a33`: `MutableStagedPerThreadMetadataCache failed to build. Exception: `

## pseudocode

```c

```

## disassembly

```asm
0x189d0  ldarg.0
0x189d1  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_OrganizationContext()
0x189d6  call     class Microsoft.Crm.Metadata.DynamicMetadataContainer Microsoft.Crm.Metadata.MetadataCache::GetStandardContainer(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x189db  isinst   Microsoft.Crm.Metadata.LockFreeMetadataContainer
0x189e0  dup
0x189e1  stloc.0
0x189e2  brtrue.s loc_189FA
0x189e4  ldarg.0
0x189e5  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_OrganizationContext()
0x189ea  call     void Microsoft.Crm.Metadata.MetadataCache::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x189ef  ldstr    aStandardCacheM// "Standard cache must be a LockFreeMetada"...
0x189f4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x189f9  throw
0x189fa  ldarg.0
0x189fb  ldloc.0
0x189fc  ldc.i4.1
0x189fd  callvirt instance class Microsoft.Crm.Metadata.LockFreeMetadataContainer Microsoft.Crm.Metadata.LockFreeMetadataContainer::Clone(bool isStagedContainer)
0x18a02  call     instance void Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::set_Container(class Microsoft.Crm.Metadata.IMetadataContainer value)
0x18a07  ldarg.0
0x18a08  ldarg.0
0x18a09  call     instance class Microsoft.Crm.Metadata.IMetadataContainer Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_Container()
0x18a0e  ldarg.1
0x18a0f  ldarg.s  4
0x18a11  call     instance class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::BuildMetadataCacheFromMetadataContainer(class Microsoft.Crm.Metadata.IMetadataContainer container, valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x18a16  stloc.1
0x18a17  leave.s  loc_18A50
0x18a19  stloc.2
0x18a1a  ldc.i4.0
0x18a1b  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x18a20  call     void Microsoft.Crm.Caching.CacheConfiguration::set_CachedIsMutableStagedPerThreadMetadataCacheEnabled(valuetype [mscorlib]System.Nullable`1<bool> value)
0x18a25  ldloc.2
0x18a26  ldarg.0
0x18a27  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_OrganizationContext()
0x18a2c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x18a31  ldc.i4.s 0x19
0x18a33  ldstr    aMutablestagedp// "MutableStagedPerThreadMetadataCache fai"...
0x18a38  ldloc.2
0x18a39  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x18a3e  call     string [mscorlib]System.String::Concat(string, string)
0x18a43  ldc.i4.0
0x18a44  newarr   [mscorlib]System.Object
0x18a49  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x18a4e  rethrow
0x18a50  ldloc.1
0x18a51  ret
```
