# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::ProcessEntityCustomizationsForAttributes

- ea: `0x5e50`
- end: `0x5e97`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::ProcessEntityCustomizationsForAttributes`
- size: `71`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x57e0`

## callees

- `0x5e50`
- `0x6240`
- `0x6a20`

## pseudocode

```c

```

## disassembly

```asm
0x5e50  ldarg.1
0x5e51  ldstr    aAttributes// "Attributes"
0x5e56  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5e5b  stloc.0
0x5e5c  ldloc.0
0x5e5d  brfalse.s loc_5E6C
0x5e5f  ldloc.0
0x5e60  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x5e65  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x5e6a  brtrue.s loc_5E6E
0x5e6c  ldnull
0x5e6d  ret
0x5e6e  ldarg.1
0x5e6f  ldstr    aLogicalname// "LogicalName"
0x5e74  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5e79  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5e7e  stloc.1
0x5e7f  ldarg.0
0x5e80  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::get_OnDemandMetadataCache()
0x5e85  ldloc.1
0x5e86  ldc.i4.1
0x5e87  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x5e8c  stloc.2
0x5e8d  ldarg.0
0x5e8e  ldloc.0
0x5e8f  ldloc.2
0x5e90  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::ProcessAttributeCustomizations(class [System.Xml]System.Xml.XmlNode customizationAttributesNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity)
0x5e95  ldloc.1
0x5e96  ret
```
