# Microsoft.Crm.BusinessEntities.ConversionContextBase::GetMetadataCache

- ea: `0x9f120`
- end: `0x9f1f7`
- name: `Microsoft.Crm.BusinessEntities.ConversionContextBase::GetMetadataCache`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x9f110`

## callees

- `0x495b0`
- `0x4c4d0`
- `0x4e2a0`
- `0x9f0b0`
- `0x9f120`

## string_xrefs

- `0x9f160`: `CrmConversionContext.GetMetadataCache has wrong value cached. Cached value= {0} New Value={1}`
- `0x9f1b8`: `CrmConversionContext.GetMetadataCache has mismtach for OrganizationId. Context Value= {0} New value= {1}`

## pseudocode

```c

```

## disassembly

```asm
0x9f120  ldarg.0
0x9f121  ldfld    class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.BusinessEntities.ConversionContextBase::_metadataCache
0x9f126  brfalse.s loc_9F198
0x9f128  ldarg.0
0x9f129  ldfld    class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.BusinessEntities.ConversionContextBase::_metadataCache
0x9f12e  callvirt instance class Microsoft.Crm.Metadata.Organization Microsoft.Crm.Metadata.DynamicMetadataCache::get_OrganizationSettings()
0x9f133  brtrue.s loc_9F13E
0x9f135  ldarg.0
0x9f136  ldnull
0x9f137  stfld    class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.BusinessEntities.ConversionContextBase::_metadataCache
0x9f13c  br.s     loc_9F198
0x9f13e  ldarg.0
0x9f13f  ldfld    class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.BusinessEntities.ConversionContextBase::_metadataCache
0x9f144  callvirt instance class Microsoft.Crm.Metadata.Organization Microsoft.Crm.Metadata.DynamicMetadataCache::get_OrganizationSettings()
0x9f149  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.Organization::get_OrganizationId()
0x9f14e  ldarg.1
0x9f14f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9f154  brfalse.s loc_9F198
0x9f156  ldnull
0x9f157  ldarg.0
0x9f158  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ConversionContextBase::get_OrganizationId()
0x9f15d  ldc.i4.s 0x1A
0x9f15f  ldc.i4.0
0x9f160  ldstr    aCrmconversionc// "CrmConversionContext.GetMetadataCache h"...
0x9f165  ldc.i4.2
0x9f166  newarr   [mscorlib]System.Object
0x9f16b  dup
0x9f16c  ldc.i4.0
0x9f16d  ldarg.0
0x9f16e  ldfld    class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.BusinessEntities.ConversionContextBase::_metadataCache
0x9f173  callvirt instance class Microsoft.Crm.Metadata.Organization Microsoft.Crm.Metadata.DynamicMetadataCache::get_OrganizationSettings()
0x9f178  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.Organization::get_OrganizationId()
0x9f17d  box      [mscorlib]System.Guid
0x9f182  stelem.ref
0x9f183  dup
0x9f184  ldc.i4.1
0x9f185  ldarg.1
0x9f186  box      [mscorlib]System.Guid
0x9f18b  stelem.ref
0x9f18c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x9f191  ldarg.0
0x9f192  ldnull
0x9f193  stfld    class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.BusinessEntities.ConversionContextBase::_metadataCache
0x9f198  ldarg.0
0x9f199  ldfld    class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.BusinessEntities.ConversionContextBase::_metadataCache
0x9f19e  brtrue.s loc_9F1F0
0x9f1a0  ldarg.0
0x9f1a1  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ConversionContextBase::get_OrganizationId()
0x9f1a6  ldarg.1
0x9f1a7  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9f1ac  brfalse.s loc_9F1DF
0x9f1ae  ldnull
0x9f1af  ldarg.0
0x9f1b0  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ConversionContextBase::get_OrganizationId()
0x9f1b5  ldc.i4.s 0x1A
0x9f1b7  ldc.i4.0
0x9f1b8  ldstr    aCrmconversionc_0// "CrmConversionContext.GetMetadataCache h"...
0x9f1bd  ldc.i4.2
0x9f1be  newarr   [mscorlib]System.Object
0x9f1c3  dup
0x9f1c4  ldc.i4.0
0x9f1c5  ldarg.0
0x9f1c6  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ConversionContextBase::get_OrganizationId()
0x9f1cb  box      [mscorlib]System.Guid
0x9f1d0  stelem.ref
0x9f1d1  dup
0x9f1d2  ldc.i4.1
0x9f1d3  ldarg.1
0x9f1d4  box      [mscorlib]System.Guid
0x9f1d9  stelem.ref
0x9f1da  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, int32, string, object[])
0x9f1df  ldarg.0
0x9f1e0  ldarg.1
0x9f1e1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x9f1e6  call     class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x9f1eb  stfld    class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.BusinessEntities.ConversionContextBase::_metadataCache
0x9f1f0  ldarg.0
0x9f1f1  ldfld    class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.BusinessEntities.ConversionContextBase::_metadataCache
0x9f1f6  ret
```
