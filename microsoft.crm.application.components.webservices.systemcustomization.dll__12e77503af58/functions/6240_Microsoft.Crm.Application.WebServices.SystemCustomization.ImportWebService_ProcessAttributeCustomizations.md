# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::ProcessAttributeCustomizations

- ea: `0x6240`
- end: `0x637c`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::ProcessAttributeCustomizations`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5e50`

## callees

- `0x10`
- `0x390`
- `0x6240`
- `0x6380`
- `0x6480`
- `0x6520`
- `0x66b0`
- `0x6a20`
- `0x76e0`

## string_xrefs

- `0x6263`: `CustomizationXml`

## pseudocode

```c

```

## disassembly

```asm
0x6240  ldarg.1
0x6241  ldstr    aAttribute_0// "Attribute"
0x6246  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x624b  stloc.0
0x624c  ldloc.0
0x624d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x6252  stloc.1
0x6253  br       loc_6334
0x6258  ldloc.1
0x6259  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x625e  castclass [System.Xml]System.Xml.XmlNode
0x6263  ldstr    aCustomizationx// "CustomizationXml"
0x6268  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x626d  stloc.2
0x626e  ldnull
0x626f  stloc.3
0x6270  ldloc.2
0x6271  ldstr    aAttribute// "attribute"
0x6276  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x627b  ldstr    aType// "type"
0x6280  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6285  ldstr    aName// "name"
0x628a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x628f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x6294  ldstr    aLookup// "lookup"
0x6299  callvirt instance bool [mscorlib]System.String::Equals(string)
0x629e  brfalse.s loc_62B5
0x62a0  ldarg.0
0x62a1  ldarg.2
0x62a2  ldloc.2
0x62a3  ldstr    aAttribute// "attribute"
0x62a8  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x62ad  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateLookupAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, class [System.Xml]System.Xml.XmlElement customizationElement)
0x62b2  stloc.3
0x62b3  br.s     loc_6313
0x62b5  ldloc.2
0x62b6  ldarg.2
0x62b7  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCustomizationXml::GetCompleteCustomizationXml(class [System.Xml]System.Xml.XmlNode customizationElement, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity)
0x62bc  stloc.s  4
0x62be  ldloc.s  4
0x62c0  ldstr    aSchemaname// "schemaname"
0x62c5  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x62ca  ldarg.0
0x62cb  ldloc.s  4
0x62cd  ldstr    aSchemaname// "schemaname"
0x62d2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x62d7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x62dc  ldarg.2
0x62dd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x62e2  call     instance string Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::SuggestNonDuplicateSchemaNameForAttribute(string schemaName, string entityName)
0x62e7  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x62ec  ldarg.0
0x62ed  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0x62f2  ldloc.s  4
0x62f4  ldstr    aAttribute// "attribute"
0x62f9  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0x62fe  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::Execute(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0x6303  stloc.s  5
0x6305  ldarg.0
0x6306  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::get_OnDemandMetadataCache()
0x630b  ldloc.s  5
0x630d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetAttribute(valuetype [mscorlib]System.Guid)
0x6312  stloc.3
0x6313  ldarg.0
0x6314  ldloc.2
0x6315  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x631a  ldloc.3
0x631b  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateAttributeCustomizations(class [System.Xml]System.Xml.XmlNode attributeCustomizationNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute)
0x6320  leave.s  loc_6334
0x6322  stloc.s  6
0x6324  ldarg.0
0x6325  ldloc.2
0x6326  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x632b  ldloc.s  6
0x632d  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateCustomizationNodeForFailure(class [System.Xml]System.Xml.XmlNode customizationNode, class [Microsoft.Crm.Core]Microsoft.Crm.CrmException ex)
0x6332  rethrow
0x6334  ldloc.1
0x6335  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x633a  brtrue   loc_6258
0x633f  leave.s  loc_6355
0x6341  ldloc.1
0x6342  isinst   [mscorlib]System.IDisposable
0x6347  stloc.s  7
0x6349  ldloc.s  7
0x634b  brfalse.s loc_6354
0x634d  ldloc.s  7
0x634f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6354  endfinally
0x6355  ldarg.1
0x6356  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x635b  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x6360  brtrue.s loc_636F
0x6362  ldarg.1
0x6363  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x6368  ldarg.1
0x6369  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x636e  pop
0x636f  leave.s  loc_637B
0x6371  ldloc.0
0x6372  brfalse.s loc_637A
0x6374  ldloc.0
0x6375  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x637a  endfinally
0x637b  ret
```
