# Microsoft.Crm.Caching.OrganizationCache::Instance

- ea: `0x96cd0`
- end: `0x96d1a`
- name: `Microsoft.Crm.Caching.OrganizationCache::Instance`
- size: `74`
- prototype: ``
- caller_count: `30`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xb00`
- `0x1ea0`
- `0x2080`
- `0x2250`
- `0x3480`
- `0x3530`
- `0x3570`
- `0x35a0`
- `0x3620`
- `0x3640`
- `0x3a90`
- `0x3c00`
- `0x3c50`
- `0x4750`
- `0x4850`
- `0x9070`
- `0xd520`
- `0xd560`
- `0x621e0`
- `0x6e410`
- `0x80320`
- `0x80440`
- `0x80cc0`
- `0x91320`
- `0x923a0`
- `0x929a0`
- `0x92f80`
- `0x93840`
- `0x98140`
- `0x9f200`

## callees

- `0x96cd0`

## string_xrefs

- `0x96cef`: `Microsoft.Crm.Application.Components.Platform`
- `0x96cf4`: `Microsoft.Crm.Caching.OrganizationSettingsCacheLoaderProxy`
- `0x96d0a`: `Microsoft.Crm.Caching.OrganizationSettingsCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x96cd0  ldsfld   class Microsoft.Crm.Caching.OrganizationCache Microsoft.Crm.Caching.OrganizationCache::_innerCache
0x96cd5  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IOrganizationSettings>::get_IsCacheLoaderInitialized()
0x96cda  brtrue.s loc_96D14
0x96cdc  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x96ce1  brfalse.s loc_96D00
0x96ce3  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x96ce8  brtrue.s loc_96D00
0x96cea  ldsfld   class Microsoft.Crm.Caching.OrganizationCache Microsoft.Crm.Caching.OrganizationCache::_innerCache
0x96cef  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x96cf4  ldstr    aMicrosoftCrmCa_64// "Microsoft.Crm.Caching.OrganizationSetti"...
0x96cf9  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IOrganizationSettings>::SetLoader(string, string)
0x96cfe  br.s     loc_96D14
0x96d00  ldsfld   class Microsoft.Crm.Caching.OrganizationCache Microsoft.Crm.Caching.OrganizationCache::_innerCache
0x96d05  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x96d0a  ldstr    aMicrosoftCrmCa_65// "Microsoft.Crm.Caching.OrganizationSetti"...
0x96d0f  callvirt instance void class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IOrganizationSettings>::SetLoader(string, string)
0x96d14  ldsfld   class Microsoft.Crm.Caching.OrganizationCache Microsoft.Crm.Caching.OrganizationCache::_innerCache
0x96d19  ret
```
