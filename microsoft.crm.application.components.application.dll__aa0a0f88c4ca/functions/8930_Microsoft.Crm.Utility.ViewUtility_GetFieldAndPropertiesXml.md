# Microsoft.Crm.Utility.ViewUtility::GetFieldAndPropertiesXml

- ea: `0x8930`
- end: `0x8a99`
- name: `Microsoft.Crm.Utility.ViewUtility::GetFieldAndPropertiesXml`
- size: `361`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8930`

## string_xrefs

- `0x895a`: `/fieldxml`
- `0x8a0f`: `/fieldxml`
- `0x89a9`: `/fetch/entity/link-entity[attribute]`

## pseudocode

```c

```

## disassembly

```asm
0x8930  ldarg.0
0x8931  ldstr    aEntitiesEntiti// "<entities></entities>"
0x8936  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x893b  stind.ref
0x893c  ldstr    aEntities_0// "<entities>"
0x8941  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x8946  stloc.0
0x8947  ldarg.0
0x8948  ldind.ref
0x8949  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x894e  ldarg.0
0x894f  ldind.ref
0x8950  ldarg.2
0x8951  ldarg.s  6
0x8953  ldarg.s  5
0x8955  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::GetPropertiesXmlForEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x895a  ldstr    aFieldxml// "/fieldxml"
0x895f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8964  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x8969  ldc.i4.1
0x896a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x896f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x8974  pop
0x8975  ldloc.0
0x8976  ldarg.2
0x8977  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x897c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8981  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8986  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x898b  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveEntityXml(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8990  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8995  pop
0x8996  ldarg.3
0x8997  brtrue   loc_8A7F
0x899c  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x89a1  stloc.1
0x89a2  ldarg.s  4
0x89a4  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x89a9  ldstr    aFetchEntityLin_0// "/fetch/entity/link-entity[attribute]"
0x89ae  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x89b3  stloc.2
0x89b4  ldloc.2
0x89b5  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x89ba  stloc.3
0x89bb  br       loc_8A54
0x89c0  ldloc.3
0x89c1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x89c6  castclass [System.Xml]System.Xml.XmlNode
0x89cb  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x89d0  ldstr    aName// "name"
0x89d5  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x89da  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x89df  stloc.s  4
0x89e1  ldloc.1
0x89e2  ldloc.s  4
0x89e4  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x89e9  brtrue.s loc_8A54
0x89eb  ldarg.s  5
0x89ed  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x89f2  ldloc.s  4
0x89f4  ldc.i4.1
0x89f5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x89fa  starg.s  2
0x89fc  ldarg.0
0x89fd  ldind.ref
0x89fe  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x8a03  ldarg.0
0x8a04  ldind.ref
0x8a05  ldarg.2
0x8a06  ldarg.s  6
0x8a08  ldarg.s  5
0x8a0a  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.SystemCustomization.SCUtil::GetPropertiesXmlForEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8a0f  ldstr    aFieldxml// "/fieldxml"
0x8a14  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8a19  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x8a1e  ldc.i4.1
0x8a1f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::ImportNode(class [System.Xml]System.Xml.XmlNode, bool)
0x8a24  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x8a29  pop
0x8a2a  ldloc.0
0x8a2b  ldarg.2
0x8a2c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x8a31  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8a36  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8a3b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8a40  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveEntityXml(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8a45  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8a4a  pop
0x8a4b  ldloc.1
0x8a4c  ldloc.s  4
0x8a4e  ldnull
0x8a4f  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x8a54  ldloc.3
0x8a55  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8a5a  brtrue   loc_89C0
0x8a5f  leave.s  loc_8A7F
0x8a61  ldloc.3
0x8a62  isinst   [mscorlib]System.IDisposable
0x8a67  stloc.s  5
0x8a69  ldloc.s  5
0x8a6b  brfalse.s loc_8A74
0x8a6d  ldloc.s  5
0x8a6f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8a74  endfinally
0x8a75  ldloc.2
0x8a76  brfalse.s loc_8A7E
0x8a78  ldloc.2
0x8a79  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8a7e  endfinally
0x8a7f  ldloc.0
0x8a80  ldstr    aEntities_1// "</entities>"
0x8a85  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8a8a  pop
0x8a8b  ldarg.1
0x8a8c  ldloc.0
0x8a8d  callvirt instance string [mscorlib]System.Object::ToString()
0x8a92  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x8a97  stind.ref
0x8a98  ret
```
