# Microsoft.Crm.ObjectModel.ImportMapService::WriteUserIdentifierMappings

- ea: `0x1117c0`
- end: `0x11184a`
- name: `Microsoft.Crm.ObjectModel.ImportMapService::WriteUserIdentifierMappings`
- size: `138`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1111c0`
- `0x1143f0`

## callees

- `0x1117c0`

## string_xrefs

- `0x1117c1`: `sourceuseridentifierforsourcedatasourceuserlink`
- `0x1117f9`: `sourceuseridentifierforsourcedatasourceuserlink`
- `0x1117ce`: `sourceuseridentifierforsourcecrmuserlink`
- `0x111814`: `sourceuseridentifierforsourcecrmuserlink`
- `0x1117db`: `targetuseridentifierforsourcecrmuserlink`
- `0x11182f`: `targetuseridentifierforsourcecrmuserlink`
- `0x1117f3`: `SourceUserIdentifierForSourceDataSourceUserLink`
- `0x11180e`: `SourceUserIdentifierForSourceCRMUserLink`
- `0x111829`: `TargetUserIdentifierForSourceCRMUserLink`

## pseudocode

```c

```

## disassembly

```asm
0x1117c0  ldarg.2
0x1117c1  ldstr    aSourceuseriden// "sourceuseridentifierforsourcedatasource"...
0x1117c6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1117cb  brtrue.s loc_111849
0x1117cd  ldarg.2
0x1117ce  ldstr    aSourceuseriden_0// "sourceuseridentifierforsourcecrmuserlin"...
0x1117d3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1117d8  brtrue.s loc_111849
0x1117da  ldarg.2
0x1117db  ldstr    aTargetuseriden// "targetuseridentifierforsourcecrmuserlin"...
0x1117e0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x1117e5  brtrue.s loc_111849
0x1117e7  ldarg.1
0x1117e8  ldstr    aUseridentifier// "UserIdentifier"
0x1117ed  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1117f2  ldarg.1
0x1117f3  ldstr    aSourceuseriden_1// "SourceUserIdentifierForSourceDataSource"...
0x1117f8  ldarg.2
0x1117f9  ldstr    aSourceuseriden// "sourceuseridentifierforsourcedatasource"...
0x1117fe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x111803  castclass [mscorlib]System.String
0x111808  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x11180d  ldarg.1
0x11180e  ldstr    aSourceuseriden_2// "SourceUserIdentifierForSourceCRMUserLin"...
0x111813  ldarg.2
0x111814  ldstr    aSourceuseriden_0// "sourceuseridentifierforsourcecrmuserlin"...
0x111819  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11181e  castclass [mscorlib]System.String
0x111823  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x111828  ldarg.1
0x111829  ldstr    aTargetuseriden_0// "TargetUserIdentifierForSourceCRMUserLin"...
0x11182e  ldarg.2
0x11182f  ldstr    aTargetuseriden// "targetuseridentifierforsourcecrmuserlin"...
0x111834  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x111839  castclass [mscorlib]System.String
0x11183e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x111843  ldarg.1
0x111844  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x111849  ret
```
