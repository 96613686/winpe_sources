# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityMapCreate::Execute

- ea: `0x33b0`
- end: `0x3435`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityMapCreate::Execute`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb200`

## callees

- `0x33b0`

## string_xrefs

- `0x33c7`: `http://schemas.microsoft.com/crm/2009/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x33b0  ldarg.0
0x33b1  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x33b6  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x33bb  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x33c0  stloc.0
0x33c1  ldloc.0
0x33c2  ldstr    aMbs// "mbs"
0x33c7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2009/W"...
0x33cc  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x33d1  ldarg.0
0x33d2  ldstr    aMbsAutomap// "mbs:automap"
0x33d7  ldloc.0
0x33d8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x33dd  stloc.1
0x33de  ldloc.1
0x33df  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x33e4  ldarg.0
0x33e5  ldloc.1
0x33e6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x33eb  pop
0x33ec  ldstr    aEntitymap// "entitymap"
0x33f1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x33f6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x33fb  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityMap::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x3400  stloc.2
0x3401  ldloc.2
0x3402  ldarg.0
0x3403  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x3408  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::set_Data(string)
0x340d  ldloc.2
0x340e  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Create()
0x3413  ldstr    aTrue// "true"
0x3418  call     bool [mscorlib]System.String::op_Equality(string, string)
0x341d  brfalse.s loc_3434
0x341f  ldloc.2
0x3420  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x3425  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x342a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x342f  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::AutoMapEntity(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3434  ret
```
