# Microsoft.Crm.Metadata.LabelCache::TryLookupEntry

- ea: `0x1e740`
- end: `0x1e89b`
- name: `Microsoft.Crm.Metadata.LabelCache::TryLookupEntry`
- size: `347`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1e6f0`
- `0x45dd0`
- `0x45e20`
- `0x45e90`

## callees

- `0xd410`
- `0xe700`
- `0xeb50`
- `0x1e740`
- `0x1e900`
- `0x484f0`
- `0x4c720`
- `0x8d5c0`
- `0x8d5e0`

## string_xrefs

- `0x1e7f1`: `, Method: LabelCache.TryLookupEntry.`
- `0x1e86b`: `, Method: LabelCache.TryLookupEntry.`

## pseudocode

```c

```

## disassembly

```asm
0x1e740  ldarg.1
0x1e741  brtrue.s loc_1E74C
0x1e743  ldarg.s  4
0x1e745  call     int32 Microsoft.Crm.Metadata.OrganizationBaseLanguage::GetOrganizationBaseLanguage(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1e74a  starg.s  1
0x1e74c  ldarg.2
0x1e74d  ldarg.3
0x1e74e  newobj   instance void Microsoft.Crm.Metadata.LabelDictionaryKey::.ctor(valuetype [mscorlib]System.Guid objectId, string objectColumnName)
0x1e753  stloc.0
0x1e754  ldnull
0x1e755  stloc.1
0x1e756  ldarg.0
0x1e757  ldfld    class Microsoft.Crm.Metadata.OverrideLabelDictionaryCache Microsoft.Crm.Metadata.LabelCache::_orgLabelSetCache
0x1e75c  ldarg.1
0x1e75d  ldarg.s  4
0x1e75f  callvirt instance var<u1> class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<int32, class Microsoft.Crm.Metadata.LabelDictionary>::LookupEntry(void, var<u1>)
0x1e764  ldloc.0
0x1e765  ldloca.s 1
0x1e767  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class Microsoft.Crm.Metadata.LabelDictionaryKey, class Microsoft.Crm.Metadata.Label>::TryGetValue(var<u1>, !!T0)
0x1e76c  brtrue.s loc_1E7A7
0x1e76e  ldarg.0
0x1e76f  ldarg.1
0x1e770  ldarg.s  4
0x1e772  ldloca.s 2
0x1e774  call     instance bool Microsoft.Crm.Metadata.LabelCache::TryGetOrganizationLanguagePackVersionData(int32 languageCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, [out] class Microsoft.Crm.Caching.OrganizationLanguagePackVersionCacheData& cacheData)
0x1e779  brfalse.s loc_1E7A7
0x1e77b  ldloc.2
0x1e77c  callvirt instance bool Microsoft.Crm.Caching.OrganizationLanguagePackVersionCacheData::get_IsCacheSharingEnabled()
0x1e781  brfalse.s loc_1E7A7
0x1e783  ldarg.1
0x1e784  ldloc.2
0x1e785  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Caching.OrganizationLanguagePackVersionCacheData::get_LanguagePackVersion()
0x1e78a  newobj   instance void Microsoft.Crm.Metadata.SystemLabelDictionaryCacheKey::.ctor(int32 languageCode, class [mscorlib]System.Version orgLanguagePackVersion)
0x1e78f  stloc.3
0x1e790  ldarg.0
0x1e791  ldfld    class Microsoft.Crm.Metadata.SystemLabelDictionaryCache Microsoft.Crm.Metadata.LabelCache::_systemLabelSetCache
0x1e796  ldloc.3
0x1e797  ldarg.s  4
0x1e799  callvirt instance var<u1> class Microsoft.Crm.Caching.BasicCrmCache`2<class Microsoft.Crm.Metadata.SystemLabelDictionaryCacheKey, class Microsoft.Crm.Metadata.LabelDictionary>::LookupEntry(void, var<u1>)
0x1e79e  ldloc.0
0x1e79f  ldloca.s 1
0x1e7a1  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class Microsoft.Crm.Metadata.LabelDictionaryKey, class Microsoft.Crm.Metadata.Label>::TryGetValue(var<u1>, !!T0)
0x1e7a6  pop
0x1e7a7  call     bool Microsoft.Crm.Platform.MetadataCacheUtil::IsLabelsMissingTelemetryEnabled()
0x1e7ac  brfalse  loc_1E899
0x1e7b1  ldloc.1
0x1e7b2  brtrue.s loc_1E821
0x1e7b4  ldc.i4.7
0x1e7b5  newarr   [mscorlib]System.Object
0x1e7ba  dup
0x1e7bb  ldc.i4.0
0x1e7bc  ldstr    aNullLabelRetur// "Null Label returned, ObjectId: "
0x1e7c1  stelem.ref
0x1e7c2  dup
0x1e7c3  ldc.i4.1
0x1e7c4  ldarga.s 2
0x1e7c6  constrained. [mscorlib]System.Guid
0x1e7cc  callvirt instance string [mscorlib]System.Object::ToString()
0x1e7d1  stelem.ref
0x1e7d2  dup
0x1e7d3  ldc.i4.2
0x1e7d4  ldstr    aColumnname// ", ColumnName: "
0x1e7d9  stelem.ref
0x1e7da  dup
0x1e7db  ldc.i4.3
0x1e7dc  ldarg.3
0x1e7dd  stelem.ref
0x1e7de  dup
0x1e7df  ldc.i4.4
0x1e7e0  ldstr    aLanguagecode_0// ", LanguageCode: "
0x1e7e5  stelem.ref
0x1e7e6  dup
0x1e7e7  ldc.i4.5
0x1e7e8  ldarg.1
0x1e7e9  box      [mscorlib]System.Int32
0x1e7ee  stelem.ref
0x1e7ef  dup
0x1e7f0  ldc.i4.6
0x1e7f1  ldstr    aMethodLabelcac// ", Method: LabelCache.TryLookupEntry."
0x1e7f6  stelem.ref
0x1e7f7  call     string [mscorlib]System.String::Concat(object[])
0x1e7fc  stloc.s  4
0x1e7fe  ldc.i4   0x80040216
0x1e803  ldc.i4.0
0x1e804  newarr   [mscorlib]System.Object
0x1e809  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1e80e  ldarg.s  4
0x1e810  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1e815  ldc.i4.s 0x14
0x1e817  ldloc.s  4
0x1e819  ldnull
0x1e81a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e81f  br.s     loc_1E899
0x1e821  ldloc.1
0x1e822  callvirt instance string Microsoft.Crm.Metadata.Label::get_Description()
0x1e827  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1e82c  brfalse.s loc_1E899
0x1e82e  ldc.i4.7
0x1e82f  newarr   [mscorlib]System.Object
0x1e834  dup
0x1e835  ldc.i4.0
0x1e836  ldstr    aNullEmptyLabel// "Null/Empty LabelDescription, ObjectId: "
0x1e83b  stelem.ref
0x1e83c  dup
0x1e83d  ldc.i4.1
0x1e83e  ldarga.s 2
0x1e840  constrained. [mscorlib]System.Guid
0x1e846  callvirt instance string [mscorlib]System.Object::ToString()
0x1e84b  stelem.ref
0x1e84c  dup
0x1e84d  ldc.i4.2
0x1e84e  ldstr    aColumnname// ", ColumnName: "
0x1e853  stelem.ref
0x1e854  dup
0x1e855  ldc.i4.3
0x1e856  ldarg.3
0x1e857  stelem.ref
0x1e858  dup
0x1e859  ldc.i4.4
0x1e85a  ldstr    aLanguagecode_0// ", LanguageCode: "
0x1e85f  stelem.ref
0x1e860  dup
0x1e861  ldc.i4.5
0x1e862  ldarg.1
0x1e863  box      [mscorlib]System.Int32
0x1e868  stelem.ref
0x1e869  dup
0x1e86a  ldc.i4.6
0x1e86b  ldstr    aMethodLabelcac// ", Method: LabelCache.TryLookupEntry."
0x1e870  stelem.ref
0x1e871  call     string [mscorlib]System.String::Concat(object[])
0x1e876  stloc.s  5
0x1e878  ldc.i4   0x80040216
0x1e87d  ldc.i4.0
0x1e87e  newarr   [mscorlib]System.Object
0x1e883  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1e888  ldarg.s  4
0x1e88a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1e88f  ldc.i4.s 0x14
0x1e891  ldloc.s  5
0x1e893  ldnull
0x1e894  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e899  ldloc.1
0x1e89a  ret
```
