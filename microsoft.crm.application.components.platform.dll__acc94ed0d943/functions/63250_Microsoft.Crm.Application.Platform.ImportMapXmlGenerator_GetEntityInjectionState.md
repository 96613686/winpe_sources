# Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::GetEntityInjectionState

- ea: `0x63250`
- end: `0x632cd`
- name: `Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::GetEntityInjectionState`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x62570`

## callees

- `0xee20`
- `0x63250`

## string_xrefs

- `0x63251`: `CustomizationXml/ShortLogicalName`
- `0x6329c`: `CustomizationXml/PrimaryKeyShortLogicalName`

## pseudocode

```c

```

## disassembly

```asm
0x63250  ldarg.1
0x63251  ldstr    aCustomizationx// "CustomizationXml/ShortLogicalName"
0x63256  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6325b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x63260  stloc.0
0x63261  ldarg.2
0x63262  ldloc.0
0x63263  call     string [mscorlib]System.String::Concat(string, string)
0x63268  stloc.1
0x63269  ldarg.3
0x6326a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6326f  ldloc.1
0x63270  ldc.i4.1
0x63271  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x63276  stloc.2
0x63277  ldloc.2
0x63278  brtrue.s loc_6327C
0x6327a  ldc.i4.0
0x6327b  ret
0x6327c  ldloc.2
0x6327d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x63282  ldc.i4.s 0x20
0x63284  ldarg.3
0x63285  call     bool Microsoft.Crm.Security.User::GetPrivilege(int32 objectType, valuetype Microsoft.Crm.Application.Types.PrivilegeId privilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6328a  brfalse.s loc_632CB
0x6328c  ldloc.2
0x6328d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x63292  ldc.i4.1
0x63293  ldarg.3
0x63294  call     bool Microsoft.Crm.Security.User::GetPrivilege(int32 objectType, valuetype Microsoft.Crm.Application.Types.PrivilegeId privilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x63299  brfalse.s loc_632CB
0x6329b  ldarg.1
0x6329c  ldstr    aCustomizationx_2// "CustomizationXml/PrimaryKeyShortLogical"...
0x632a1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x632a6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x632ab  stloc.3
0x632ac  ldarg.2
0x632ad  ldloc.3
0x632ae  call     string [mscorlib]System.String::Concat(string, string)
0x632b3  stloc.s  4
0x632b5  ldloc.2
0x632b6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x632bb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x632c0  ldloc.s  4
0x632c2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x632c7  brfalse.s loc_632CB
0x632c9  ldc.i4.1
0x632ca  ret
0x632cb  ldc.i4.2
0x632cc  ret
```
