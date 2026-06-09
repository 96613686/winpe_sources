# Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance

- ea: `0x96780`
- end: `0x967f6`
- name: `Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance`
- size: `118`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3920`
- `0x3960`
- `0x4670`
- `0x1e900`
- `0x708f0`
- `0x7a180`
- `0x7b340`
- `0x80320`
- `0x80420`

## callees

- `0x96780`
- `0x96800`

## string_xrefs

- `0x96787`: `Microsoft.Crm.Application.Components.Platform`
- `0x9678d`: `Microsoft.Crm.Caching.OrganizationBuildVersionCacheLoaderProxy`
- `0x9679b`: `Microsoft.Crm.Caching.OrganizationBuildVersionCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x96780  call     bool Microsoft.Crm.Caching.OrganizationBuildVersionCache::UseClientCacheLoader()
0x96785  brfalse.s loc_96795
0x96787  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x9678c  stloc.0
0x9678d  ldstr    aMicrosoftCrmCa_61// "Microsoft.Crm.Caching.OrganizationBuild"...
0x96792  stloc.1
0x96793  br.s     loc_967A1
0x96795  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x9679a  stloc.0
0x9679b  ldstr    aMicrosoftCrmCa_62// "Microsoft.Crm.Caching.OrganizationBuild"...
0x967a0  stloc.1
0x967a1  ldsfld   class Microsoft.Crm.Caching.OrganizationBuildVersionCache Microsoft.Crm.Caching.OrganizationBuildVersionCache::_innerCache
0x967a6  callvirt instance class Microsoft.Crm.Caching.ICacheLoader`2<var<u1>, !!T0> class Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.VersionCacheData>::get_CacheLoader()
0x967ab  brtrue.s loc_967BB
0x967ad  ldsfld   class Microsoft.Crm.Caching.OrganizationBuildVersionCache Microsoft.Crm.Caching.OrganizationBuildVersionCache::_innerCache
0x967b2  ldloc.0
0x967b3  ldloc.1
0x967b4  callvirt instance void class Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.VersionCacheData>::SetLoader(string, string)
0x967b9  br.s     loc_967F0
0x967bb  ldsfld   class [mscorlib]System.Lazy`1<bool> class Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.VersionCacheData>::IsClientContext
0x967c0  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x967c5  brfalse.s loc_967F0
0x967c7  ldsfld   class Microsoft.Crm.Caching.OrganizationBuildVersionCache Microsoft.Crm.Caching.OrganizationBuildVersionCache::_innerCache
0x967cc  callvirt instance class Microsoft.Crm.Caching.ICacheLoader`2<var<u1>, !!T0> class Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.VersionCacheData>::get_CacheLoader()
0x967d1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x967d6  callvirt instance string [mscorlib]System.Type::get_FullName()
0x967db  ldloc.1
0x967dc  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x967e1  brfalse.s loc_967F0
0x967e3  ldsfld   class Microsoft.Crm.Caching.OrganizationBuildVersionCache Microsoft.Crm.Caching.OrganizationBuildVersionCache::_innerCache
0x967e8  ldloc.0
0x967e9  ldloc.1
0x967ea  ldc.i4.0
0x967eb  callvirt instance void class Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.VersionCacheData>::SetLoader(string, string, bool)
0x967f0  ldsfld   class Microsoft.Crm.Caching.OrganizationBuildVersionCache Microsoft.Crm.Caching.OrganizationBuildVersionCache::_innerCache
0x967f5  ret
```
