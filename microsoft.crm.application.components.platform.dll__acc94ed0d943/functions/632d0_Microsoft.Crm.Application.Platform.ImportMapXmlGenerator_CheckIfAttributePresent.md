# Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::CheckIfAttributePresent

- ea: `0x632d0`
- end: `0x6330c`
- name: `Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::CheckIfAttributePresent`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x62980`

## callees

- `0x632d0`

## string_xrefs

- `0x632e1`: `createdon`
- `0x632f2`: `createdon`

## pseudocode

```c

```

## disassembly

```asm
0x632d0  ldarg.s  4
0x632d2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x632d7  ldarg.1
0x632d8  ldc.i4.1
0x632d9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x632de  stloc.0
0x632df  ldarg.2
0x632e0  ldarg.3
0x632e1  ldstr    aCreatedon// "createdon"
0x632e6  call     string [mscorlib]System.String::Concat(string, string)
0x632eb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x632f0  brfalse.s loc_632F9
0x632f2  ldstr    aCreatedon// "createdon"
0x632f7  starg.s  2
0x632f9  ldloc.0
0x632fa  brtrue.s loc_632FE
0x632fc  ldc.i4.0
0x632fd  ret
0x632fe  ldloc.0
0x632ff  ldarg.2
0x63300  ldc.i4.1
0x63301  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x63306  brtrue.s loc_6330A
0x63308  ldc.i4.0
0x63309  ret
0x6330a  ldc.i4.1
0x6330b  ret
```
