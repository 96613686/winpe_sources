# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateEntity

- ea: `0x5ed0`
- end: `0x5f88`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateEntity`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5d20`

## callees

- `0x10`
- `0x26f0`
- `0x5ed0`
- `0x5f90`
- `0x6430`
- `0x66b0`
- `0x6a20`
- `0x6ef0`
- `0x6f00`
- `0x6f60`
- `0x7050`

## string_xrefs

- `0x5f76`: `CustomizationXml`
- `0x5f1f`: `CustomizationXml/PrimaryKey`

## pseudocode

```c

```

## disassembly

```asm
0x5ed0  ldarg.1
0x5ed1  newobj   instance void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::.ctor(class [System.Xml]System.Xml.XPath.IXPathNavigable entityCustomizationNode)
0x5ed6  stloc.0
0x5ed7  ldloc.0
0x5ed8  ldarg.0
0x5ed9  ldloc.0
0x5eda  callvirt instance string Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::get_SchemaName()
0x5edf  call     instance string Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::SuggestNonDuplicateSchemaNameForEntity(string schemaName)
0x5ee4  callvirt instance void Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::set_SchemaName(string value)
0x5ee9  ldloc.0
0x5eea  callvirt instance string Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCustomizationXml::GenerateXml()
0x5eef  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x5ef4  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x5ef9  ldstr    aEntity// "entity"
0x5efe  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0x5f03  stloc.1
0x5f04  ldarg.0
0x5f05  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0x5f0a  ldloc.1
0x5f0b  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.EntityCreate::Execute(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x5f10  stloc.3
0x5f11  ldarg.0
0x5f12  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::get_OnDemandMetadataCache()
0x5f17  ldloc.3
0x5f18  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x5f1d  stloc.2
0x5f1e  ldarg.1
0x5f1f  ldstr    aCustomizationx_0// "CustomizationXml/PrimaryKey"
0x5f24  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5f29  dup
0x5f2a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5f2f  stloc.s  4
0x5f31  ldloc.2
0x5f32  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x5f37  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x5f3c  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x5f41  ldarg.0
0x5f42  ldarg.1
0x5f43  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x5f48  ldarg.1
0x5f49  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5f4e  ldstr    aId_0// "Id"
0x5f53  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5f58  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5f5d  ldloc.2
0x5f5e  ldloc.s  4
0x5f60  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateEntityMapping(class [System.Xml]System.Xml.XmlDocument mapDoc, string entityRef, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, string oldPrimaryFieldName)
0x5f65  leave.s  loc_5F74
0x5f67  stloc.s  5
0x5f69  ldarg.0
0x5f6a  ldarg.1
0x5f6b  ldloc.s  5
0x5f6d  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateCustomizationNodeForFailure(class [System.Xml]System.Xml.XmlNode customizationNode, class [Microsoft.Crm.Core]Microsoft.Crm.CrmException ex)
0x5f72  rethrow
0x5f74  ldarg.1
0x5f75  ldarg.1
0x5f76  ldstr    aCustomizationx// "CustomizationXml"
0x5f7b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5f80  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x5f85  pop
0x5f86  ldloc.2
0x5f87  ret
```
