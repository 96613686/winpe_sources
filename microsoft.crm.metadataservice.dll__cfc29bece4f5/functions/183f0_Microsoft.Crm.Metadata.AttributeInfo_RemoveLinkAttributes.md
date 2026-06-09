# Microsoft.Crm.Metadata.AttributeInfo::RemoveLinkAttributes

- ea: `0x183f0`
- end: `0x1843f`
- name: `Microsoft.Crm.Metadata.AttributeInfo::RemoveLinkAttributes`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1e420`

## callees

- `0x183f0`
- `0x18760`

## string_xrefs

- `0x183f6`: `linkedattributeid`
- `0x1840d`: `linkedattributeid`

## pseudocode

```c

```

## disassembly

```asm
0x183f0  ldarg.0
0x183f1  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x183f6  ldstr    aLinkedattribut// "linkedattributeid"
0x183fb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x18400  brfalse.s loc_18417
0x18402  ldarg.0
0x18403  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x18408  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x1840d  ldstr    aLinkedattribut// "linkedattributeid"
0x18412  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::Remove(string)
0x18417  ldarg.0
0x18418  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1841d  ldstr    aYomiof// "yomiof"
0x18422  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x18427  brfalse.s loc_1843E
0x18429  ldarg.0
0x1842a  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x1842f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::get_InnerEntityData()
0x18434  ldstr    aYomiof// "yomiof"
0x18439  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::Remove(string)
0x1843e  ret
```
