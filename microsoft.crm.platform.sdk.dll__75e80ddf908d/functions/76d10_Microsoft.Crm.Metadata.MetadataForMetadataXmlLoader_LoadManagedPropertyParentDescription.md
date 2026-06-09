# Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::LoadManagedPropertyParentDescription

- ea: `0x76d10`
- end: `0x76d57`
- name: `Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::LoadManagedPropertyParentDescription`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x76ce0`

## callees

- `0x716f0`
- `0x76d10`
- `0x771e0`
- `0x77200`

## string_xrefs

- `0x76d1e`: `ParentComponentType`
- `0x76d2e`: `LinkingAttributeName`

## pseudocode

```c

```

## disassembly

```asm
0x76d10  ldarg.0
0x76d11  brfalse.s loc_76D1B
0x76d13  ldarg.0
0x76d14  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x76d19  brtrue.s loc_76D1D
0x76d1b  ldnull
0x76d1c  ret
0x76d1d  ldarg.0
0x76d1e  ldstr    aParentcomponen// "ParentComponentType"
0x76d23  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x76d28  call     int32 Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetInt32FromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x76d2d  ldarg.0
0x76d2e  ldstr    aLinkingattribu// "LinkingAttributeName"
0x76d33  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x76d38  call     string Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetStringFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x76d3d  stloc.0
0x76d3e  ldarg.0
0x76d3f  ldstr    aControllingatt// "ControllingAttributeName"
0x76d44  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x76d49  call     string Microsoft.Crm.Metadata.MetadataForMetadataXmlLoader::GetStringFromXmlNode(class [System.Xml]System.Xml.XmlNode xmlNode)
0x76d4e  stloc.1
0x76d4f  ldloc.0
0x76d50  ldloc.1
0x76d51  newobj   instance void Microsoft.Crm.Metadata.MetadataManagedPropertyParentMetadataDescription::.ctor(int32 parentComponentType, string linkingAttributeName, string controllingAttributeName)
0x76d56  ret
```
