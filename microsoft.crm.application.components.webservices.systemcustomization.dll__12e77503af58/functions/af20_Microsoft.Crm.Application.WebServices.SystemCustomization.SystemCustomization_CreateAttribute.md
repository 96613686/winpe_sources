# Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateAttribute

- ea: `0xaf20`
- end: `0xafc7`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::CreateAttribute`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x10`
- `0x390`
- `0x20e0`
- `0x9e50`
- `0xa4c0`
- `0xa530`
- `0xa550`
- `0xaf20`

## pseudocode

```c

```

## disassembly

```asm
0xaf20  ldarg.1
0xaf21  call     bool Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipDataConverter::CanConvert(class [System.Xml]System.Xml.XmlNode attributeData)
0xaf26  brfalse.s loc_AFA3
0xaf28  ldarg.0
0xaf29  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xaf2e  ldarg.1
0xaf2f  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipDataConverter::GetRelationshipNode(class [System.Xml]System.Xml.XmlNode attributeData)
0xaf34  ldstr    aRelationship// "relationship"
0xaf39  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0xaf3e  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::Execute(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0xaf43  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipDataConverter::GetAttributeFromRelationship(valuetype [mscorlib]System.Guid relationshipId)
0xaf48  stloc.0
0xaf49  ldarg.1
0xaf4a  ldstr    aAttributeid// "attributeid"
0xaf4f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xaf54  ldloca.s 0
0xaf56  ldstr    aB// "B"
0xaf5b  call     instance string [mscorlib]System.Guid::ToString(string)
0xaf60  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0xaf65  ldarg.1
0xaf66  ldstr    aType// "type"
0xaf6b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xaf70  callvirt instance void [System.Xml]System.Xml.XmlNode::RemoveAll()
0xaf75  ldarg.1
0xaf76  ldstr    aSchemaname// "schemaname"
0xaf7b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0xaf80  stloc.1
0xaf81  ldarg.1
0xaf82  ldloc.1
0xaf83  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0xaf88  pop
0xaf89  ldarg.0
0xaf8a  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xaf8f  ldarg.1
0xaf90  ldstr    aAttribute// "attribute"
0xaf95  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0xaf9a  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeUpdate::Execute(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0xaf9f  ldloc.0
0xafa0  stloc.2
0xafa1  leave.s  loc_AFC5
0xafa3  ldarg.0
0xafa4  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::get_SolutionId()
0xafa9  ldarg.1
0xafaa  ldstr    aAttribute// "attribute"
0xafaf  newobj   instance void Microsoft.Crm.Application.WebServices.ParameterBag::.ctor(class [System.Xml]System.Xml.XmlNode parameterBag, string name)
0xafb4  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::Execute(valuetype [mscorlib]System.Guid solutionId, class Microsoft.Crm.Application.WebServices.ParameterBag paramBag)
0xafb9  stloc.2
0xafba  leave.s  loc_AFC5
0xafbc  stloc.3
0xafbd  ldarg.0
0xafbe  ldloc.3
0xafbf  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0xafc4  throw
0xafc5  ldloc.2
0xafc6  ret
```
