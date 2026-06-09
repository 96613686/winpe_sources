# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateLookupAttribute

- ea: `0x6380`
- end: `0x6427`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateLookupAttribute`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x6240`

## callees

- `0x10`
- `0x6480`
- `0x64d0`
- `0x6a20`
- `0x6ab0`
- `0x6ac0`
- `0x6ad0`
- `0x6ae0`
- `0x6ba0`
- `0x6cd0`
- `0x9e50`

## pseudocode

```c

```

## disassembly

```asm
0x6380  ldarg.2
0x6381  ldstr    aType// "type"
0x6386  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x638b  ldstr    aEntity// "entity"
0x6390  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6395  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x639a  ldarg.2
0x639b  ldstr    aDisplayname// "displayname"
0x63a0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x63a5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x63aa  stloc.0
0x63ab  ldloc.0
0x63ac  ldarg.1
0x63ad  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x63b2  newobj   instance void Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::.ctor(string referencedEntityName, string referencedInstanceName, string referencingEntityName)
0x63b7  stloc.1
0x63b8  ldloc.1
0x63b9  ldarg.0
0x63ba  ldloc.1
0x63bb  callvirt instance string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::get_RelationshipSchemaName()
0x63c0  call     instance string Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::SuggestNonDuplicateSchemaNameForRelationship(string schemaName)
0x63c5  callvirt instance void Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::set_RelationshipSchemaName(string value)
0x63ca  ldloc.1
0x63cb  ldarg.0
0x63cc  ldloc.1
0x63cd  callvirt instance string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::get_AttributeSchemaName()
0x63d2  ldarg.1
0x63d3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x63d8  call     instance string Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::SuggestNonDuplicateSchemaNameForAttribute(string schemaName, string entityName)
0x63dd  callvirt instance void Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::set_AttributeSchemaName(string value)
0x63e2  ldloc.1
0x63e3  callvirt instance string Microsoft.Crm.Application.WebServices.SystemCustomization.LookupCustomizationXml::GenerateXml()
0x63e8  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x63ed  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x63f2  stloc.2
0x63f3  ldarg.0
0x63f4  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0x63f9  ldloc.2
0x63fa  ldstr    aRelationship// "relationship"
0x63ff  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0x6404  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::Execute(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x6409  stloc.3
0x640a  ldarg.0
0x640b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::get_OnDemandMetadataCache()
0x6410  ldloc.3
0x6411  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntityRelationship(valuetype [mscorlib]System.Guid)
0x6416  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationship::get_Relationships()
0x641b  ldc.i4.0
0x641c  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataArrayList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship>::get_Item(!!T0)
0x6421  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0x6426  ret
```
