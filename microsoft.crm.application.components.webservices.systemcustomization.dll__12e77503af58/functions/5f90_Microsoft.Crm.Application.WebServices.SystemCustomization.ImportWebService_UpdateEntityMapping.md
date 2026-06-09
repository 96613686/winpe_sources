# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateEntityMapping

- ea: `0x5f90`
- end: `0x623d`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateEntityMapping`
- size: `685`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x5ed0`

## callees

- `0x5f90`

## string_xrefs

- `0x60d3`: `/Map/Customizations/Entities/Entity/Attributes/Attribute/CustomizationXml/attribute/type[entity='`

## pseudocode

```c

```

## disassembly

```asm
0x5f90  ldarg.1
0x5f91  ldc.i4.5
0x5f92  newarr   [mscorlib]System.String
0x5f97  dup
0x5f98  ldc.i4.0
0x5f99  ldstr    aMapEntitymapsE_0// "/Map/EntityMaps/EntityMap[not(@Unused) "...
0x5f9e  stelem.ref
0x5f9f  dup
0x5fa0  ldc.i4.1
0x5fa1  ldc.i4.3
0x5fa2  stloc.1
0x5fa3  ldloca.s 1
0x5fa5  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x5fab  callvirt instance string [mscorlib]System.Object::ToString()
0x5fb0  stelem.ref
0x5fb1  dup
0x5fb2  ldc.i4.2
0x5fb3  ldstr    aAndTargetentit// "' and @TargetEntityRef='"
0x5fb8  stelem.ref
0x5fb9  dup
0x5fba  ldc.i4.3
0x5fbb  ldarg.2
0x5fbc  stelem.ref
0x5fbd  dup
0x5fbe  ldc.i4.4
0x5fbf  ldstr    asc_E1E0// "']"
0x5fc4  stelem.ref
0x5fc5  call     string [mscorlib]System.String::Concat(string[])
0x5fca  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x5fcf  stloc.0
0x5fd0  ldloc.0
0x5fd1  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5fd6  stloc.2
0x5fd7  br       loc_60A7
0x5fdc  ldloc.2
0x5fdd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5fe2  castclass [System.Xml]System.Xml.XmlNode
0x5fe7  stloc.3
0x5fe8  ldloc.3
0x5fe9  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5fee  ldstr    aTargetentityna_0// "TargetEntityName"
0x5ff3  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5ff8  ldarg.3
0x5ff9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x5ffe  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x6003  ldloc.3
0x6004  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6009  ldloc.3
0x600a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x600f  ldstr    aTargetentityre// "TargetEntityRef"
0x6014  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x6019  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Remove(class [System.Xml]System.Xml.XmlAttribute)
0x601e  pop
0x601f  ldloc.3
0x6020  ldstr    aAttributemapsA_0// "AttributeMaps/AttributeMap[not(@Unused)"...
0x6025  ldarg.s  4
0x6027  ldstr    asc_E1E0// "']"
0x602c  call     string [mscorlib]System.String::Concat(string, string, string)
0x6031  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6036  stloc.s  4
0x6038  ldloc.s  4
0x603a  brfalse.s loc_6083
0x603c  ldloc.3
0x603d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6042  ldstr    aProcesscode// "ProcessCode"
0x6047  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x604c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x6051  ldc.i4.3
0x6052  stloc.1
0x6053  ldloca.s 1
0x6055  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x605b  callvirt instance string [mscorlib]System.Object::ToString()
0x6060  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6065  brfalse.s loc_6083
0x6067  ldloc.s  4
0x6069  ldstr    aTargetattribut// "TargetAttributeName"
0x606e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6073  ldarg.3
0x6074  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x6079  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x607e  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x6083  ldloc.3
0x6084  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6089  ldstr    aProcesscode// "ProcessCode"
0x608e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x6093  ldc.i4.2
0x6094  stloc.1
0x6095  ldloca.s 1
0x6097  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x609d  callvirt instance string [mscorlib]System.Object::ToString()
0x60a2  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x60a7  ldloc.2
0x60a8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x60ad  brtrue   loc_5FDC
0x60b2  leave.s  loc_60D2
0x60b4  ldloc.2
0x60b5  isinst   [mscorlib]System.IDisposable
0x60ba  stloc.s  5
0x60bc  ldloc.s  5
0x60be  brfalse.s loc_60C7
0x60c0  ldloc.s  5
0x60c2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x60c7  endfinally
0x60c8  ldloc.0
0x60c9  brfalse.s loc_60D1
0x60cb  ldloc.0
0x60cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x60d1  endfinally
0x60d2  ldarg.1
0x60d3  ldstr    aMapCustomizati// "/Map/Customizations/Entities/Entity/Att"...
0x60d8  ldarg.2
0x60d9  ldstr    aAndNameLookup// "' and name='lookup']"
0x60de  call     string [mscorlib]System.String::Concat(string, string, string)
0x60e3  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x60e8  stloc.s  6
0x60ea  ldloc.s  6
0x60ec  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x60f1  stloc.2
0x60f2  br.s     loc_6114
0x60f4  ldloc.2
0x60f5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x60fa  castclass [System.Xml]System.Xml.XmlNode
0x60ff  ldstr    aEntity// "entity"
0x6104  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6109  ldarg.3
0x610a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x610f  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x6114  ldloc.2
0x6115  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x611a  brtrue.s loc_60F4
0x611c  leave.s  loc_613E
0x611e  ldloc.2
0x611f  isinst   [mscorlib]System.IDisposable
0x6124  stloc.s  5
0x6126  ldloc.s  5
0x6128  brfalse.s loc_6131
0x612a  ldloc.s  5
0x612c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6131  endfinally
0x6132  ldloc.s  6
0x6134  brfalse.s loc_613D
0x6136  ldloc.s  6
0x6138  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x613d  endfinally
0x613e  ldarg.1
0x613f  ldstr    aMapEntitymapsE_1// "/Map/EntityMaps/EntityMap/AttributeMaps"...
0x6144  ldarg.2
0x6145  ldstr    aAndLookuptypeS// "' and LookupType='System']"
0x614a  call     string [mscorlib]System.String::Concat(string, string, string)
0x614f  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x6154  stloc.s  7
0x6156  ldloc.s  7
0x6158  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x615d  stloc.2
0x615e  br.s     loc_6180
0x6160  ldloc.2
0x6161  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6166  castclass [System.Xml]System.Xml.XmlNode
0x616b  ldstr    aLookupentityna// "LookupEntityName"
0x6170  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6175  ldarg.3
0x6176  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x617b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x6180  ldloc.2
0x6181  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6186  brtrue.s loc_6160
0x6188  leave.s  loc_61AA
0x618a  ldloc.2
0x618b  isinst   [mscorlib]System.IDisposable
0x6190  stloc.s  5
0x6192  ldloc.s  5
0x6194  brfalse.s loc_619D
0x6196  ldloc.s  5
0x6198  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x619d  endfinally
0x619e  ldloc.s  7
0x61a0  brfalse.s loc_61A9
0x61a2  ldloc.s  7
0x61a4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61a9  endfinally
0x61aa  ldarg.1
0x61ab  ldc.i4.5
0x61ac  newarr   [mscorlib]System.String
0x61b1  dup
0x61b2  ldc.i4.0
0x61b3  ldstr    aMapEntitymapsE_2// "/Map/EntityMaps/EntityMap/AttributeMaps"...
0x61b8  stelem.ref
0x61b9  dup
0x61ba  ldc.i4.1
0x61bb  ldarg.s  4
0x61bd  stelem.ref
0x61be  dup
0x61bf  ldc.i4.2
0x61c0  ldstr    aAndLookupentit// "' and LookupEntityName ='"
0x61c5  stelem.ref
0x61c6  dup
0x61c7  ldc.i4.3
0x61c8  ldarg.3
0x61c9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x61ce  stelem.ref
0x61cf  dup
0x61d0  ldc.i4.4
0x61d1  ldstr    asc_E1E0// "']"
0x61d6  stelem.ref
0x61d7  call     string [mscorlib]System.String::Concat(string[])
0x61dc  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x61e1  stloc.s  8
0x61e3  ldloc.s  8
0x61e5  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x61ea  stloc.2
0x61eb  br.s     loc_6212
0x61ed  ldloc.2
0x61ee  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x61f3  castclass [System.Xml]System.Xml.XmlNode
0x61f8  ldstr    aLookupattribut// "LookupAttributeName"
0x61fd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6202  ldarg.3
0x6203  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryField()
0x6208  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x620d  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x6212  ldloc.2
0x6213  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6218  brtrue.s loc_61ED
0x621a  leave.s  loc_623C
0x621c  ldloc.2
0x621d  isinst   [mscorlib]System.IDisposable
0x6222  stloc.s  5
0x6224  ldloc.s  5
0x6226  brfalse.s loc_622F
0x6228  ldloc.s  5
0x622a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x622f  endfinally
0x6230  ldloc.s  8
0x6232  brfalse.s loc_623B
0x6234  ldloc.s  8
0x6236  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x623b  endfinally
0x623c  ret
```
