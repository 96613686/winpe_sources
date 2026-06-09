# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetMetadataCache

- ea: `0x1f210`
- end: `0x1f27c`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetMetadataCache`
- size: `108`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xf670`
- `0xf690`
- `0xfde0`
- `0xffb0`
- `0x14630`
- `0x149d0`
- `0x1a370`
- `0x1c620`
- `0x1db20`
- `0x1f380`
- `0x1f800`
- `0x1f840`
- `0x1f870`
- `0x1ff90`
- `0x21ca0`
- `0x22080`
- `0x22260`
- `0x225f0`
- `0x25fc0`
- `0x271e0`

## callees

- `0x1f210`
- `0x20020`

## string_xrefs

- `0x1f238`: `OData.DynamicMetadataCacheLocal`
- `0x1f24e`: `OData.DynamicMetadataCacheLocal`
- `0x1f26c`: `OData.DynamicMetadataCacheLocal`

## pseudocode

```c

```

## disassembly

```asm
0x1f210  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1f215  brfalse.s loc_1F223
0x1f217  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1f21c  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x1f221  brtrue.s loc_1F22E
0x1f223  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetOrganizationContext()
0x1f228  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f22d  ret
0x1f22e  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1f233  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x1f238  ldstr    aOdataDynamicme// "OData.DynamicMetadataCacheLocal"
0x1f23d  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x1f242  brtrue.s loc_1F262
0x1f244  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1f249  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x1f24e  ldstr    aOdataDynamicme// "OData.DynamicMetadataCacheLocal"
0x1f253  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetOrganizationContext()
0x1f258  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f25d  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x1f262  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1f267  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x1f26c  ldstr    aOdataDynamicme// "OData.DynamicMetadataCacheLocal"
0x1f271  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x1f276  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache
0x1f27b  ret
```
