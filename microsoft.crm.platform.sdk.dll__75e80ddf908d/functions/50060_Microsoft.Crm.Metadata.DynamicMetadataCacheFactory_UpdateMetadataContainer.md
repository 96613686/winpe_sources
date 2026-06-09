# Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::UpdateMetadataContainer

- ea: `0x50060`
- end: `0x5011d`
- name: `Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::UpdateMetadataContainer`
- size: `189`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4cd00`
- `0x4e890`

## callees

- `0x50060`
- `0x50db0`
- `0x510c0`
- `0x523c0`

## string_xrefs

- `0x50068`: `UpdateMetadataContainer - CacheType=`
- `0x5009d`: `Updating metadata cache, type = {0}, masks = {1}, orgid = {2}`

## pseudocode

```c

```

## disassembly

```asm
0x50060  ldc.i4.4
0x50061  newarr   [mscorlib]System.Object
0x50066  dup
0x50067  ldc.i4.0
0x50068  ldstr    aUpdatemetadata// "UpdateMetadataContainer - CacheType="
0x5006d  stelem.ref
0x5006e  dup
0x5006f  ldc.i4.1
0x50070  ldarg.0
0x50071  box      Microsoft.Crm.Metadata.CacheType
0x50076  stelem.ref
0x50077  dup
0x50078  ldc.i4.2
0x50079  ldstr    aLoadmasks// " LoadMasks="
0x5007e  stelem.ref
0x5007f  dup
0x50080  ldc.i4.3
0x50081  ldarg.1
0x50082  box      Microsoft.Crm.Metadata.LoadMasks
0x50087  stelem.ref
0x50088  call     string [mscorlib]System.String::Concat(object[])
0x5008d  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name)
0x50092  stloc.0
0x50093  ldarg.3
0x50094  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x50099  stloc.1
0x5009a  ldloc.1
0x5009b  ldc.i4.s 0x19
0x5009d  ldstr    aUpdatingMetada// "Updating metadata cache, type = {0}, ma"...
0x500a2  ldc.i4.3
0x500a3  newarr   [mscorlib]System.Object
0x500a8  dup
0x500a9  ldc.i4.0
0x500aa  ldarg.0
0x500ab  box      Microsoft.Crm.Metadata.CacheType
0x500b0  stelem.ref
0x500b1  dup
0x500b2  ldc.i4.1
0x500b3  ldarg.1
0x500b4  box      Microsoft.Crm.Metadata.LoadMasks
0x500b9  stelem.ref
0x500ba  dup
0x500bb  ldc.i4.2
0x500bc  ldloc.1
0x500bd  box      [mscorlib]System.Guid
0x500c2  stelem.ref
0x500c3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x500c8  ldarg.0
0x500c9  ldarg.3
0x500ca  call     class Microsoft.Crm.Metadata.DynamicMetadataCacheLoader Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::GetDynamicMetadataCacheLoader(valuetype Microsoft.Crm.Metadata.CacheType type, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x500cf  ldc.i4.0
0x500d0  stloc.2
0x500d1  ldarg.3
0x500d2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_ContextStorage()
0x500d7  ldsfld   string Microsoft.Crm.Platform.MetadataCacheUtil::AddStagedMetadataInCache
0x500dc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x500e1  brfalse.s loc_500F9
0x500e3  ldarg.3
0x500e4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_ContextStorage()
0x500e9  ldsfld   string Microsoft.Crm.Platform.MetadataCacheUtil::AddStagedMetadataInCache
0x500ee  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x500f3  unbox.any [mscorlib]System.Boolean
0x500f8  stloc.2
0x500f9  ldarg.1
0x500fa  ldarg.3
0x500fb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_Connection()
0x50100  ldarg.3
0x50101  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::get_Transaction()
0x50106  ldloc.0
0x50107  ldarg.2
0x50108  ldloc.2
0x50109  callvirt instance class Microsoft.Crm.Metadata.IMetadataContainer Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::UpdateMetadataContainerFromDatabase(valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction transaction, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter, class Microsoft.Crm.Metadata.DynamicMetadataCache cache, bool isInStagedContext)
0x5010e  stloc.3
0x5010f  leave.s  loc_5011B
0x50111  ldloc.0
0x50112  brfalse.s loc_5011A
0x50114  ldloc.0
0x50115  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5011a  endfinally
0x5011b  ldloc.3
0x5011c  ret
```
