# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateAttributeCustomizations

- ea: `0x6520`
- end: `0x66a8`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateAttributeCustomizations`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x6240`

## callees

- `0x6520`

## pseudocode

```c

```

## disassembly

```asm
0x6520  ldarg.2
0x6521  brtrue.s loc_6524
0x6523  ret
0x6524  ldarg.1
0x6525  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x652a  ldstr    aId_0// "Id"
0x652f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x6534  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x6539  stloc.0
0x653a  ldc.i4.5
0x653b  newarr   [mscorlib]System.String
0x6540  dup
0x6541  ldc.i4.0
0x6542  ldstr    aEntitymapsEnti// "//EntityMaps/EntityMap[(@TargetEntityNa"...
0x6547  stelem.ref
0x6548  dup
0x6549  ldc.i4.1
0x654a  ldarg.2
0x654b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x6550  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x6555  stelem.ref
0x6556  dup
0x6557  ldc.i4.2
0x6558  ldstr    aAndNotUnusedAt// "') and not(@Unused)]/AttributeMaps/Attr"...
0x655d  stelem.ref
0x655e  dup
0x655f  ldc.i4.3
0x6560  ldloc.0
0x6561  stelem.ref
0x6562  dup
0x6563  ldc.i4.4
0x6564  ldstr    asc_E1E0// "']"
0x6569  stelem.ref
0x656a  call     string [mscorlib]System.String::Concat(string[])
0x656f  stloc.1
0x6570  ldarg.1
0x6571  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x6576  ldloc.1
0x6577  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x657c  stloc.2
0x657d  ldloc.2
0x657e  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x6583  stloc.3
0x6584  br.s     loc_65DC
0x6586  ldloc.3
0x6587  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x658c  castclass [System.Xml]System.Xml.XmlNode
0x6591  dup
0x6592  ldstr    aTargetattribut_0// "TargetAttributeRef"
0x6597  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x659c  stloc.s  4
0x659e  dup
0x659f  ldloc.s  4
0x65a1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x65a6  pop
0x65a7  dup
0x65a8  ldstr    aTargetattribut// "TargetAttributeName"
0x65ad  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x65b2  ldarg.2
0x65b3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x65b8  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x65bd  ldstr    aProcesscode// "ProcessCode"
0x65c2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x65c7  ldc.i4.2
0x65c8  stloc.s  5
0x65ca  ldloca.s 5
0x65cc  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x65d2  callvirt instance string [mscorlib]System.Object::ToString()
0x65d7  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x65dc  ldloc.3
0x65dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x65e2  brtrue.s loc_6586
0x65e4  leave.s  loc_6604
0x65e6  ldloc.3
0x65e7  isinst   [mscorlib]System.IDisposable
0x65ec  stloc.s  6
0x65ee  ldloc.s  6
0x65f0  brfalse.s loc_65F9
0x65f2  ldloc.s  6
0x65f4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65f9  endfinally
0x65fa  ldloc.2
0x65fb  brfalse.s loc_6603
0x65fd  ldloc.2
0x65fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6603  endfinally
0x6604  ldarg.1
0x6605  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x660a  ldc.i4.5
0x660b  newarr   [mscorlib]System.String
0x6610  dup
0x6611  ldc.i4.0
0x6612  ldstr    aMapEntitymapsE_2// "/Map/EntityMaps/EntityMap/AttributeMaps"...
0x6617  stelem.ref
0x6618  dup
0x6619  ldc.i4.1
0x661a  ldloc.0
0x661b  stelem.ref
0x661c  dup
0x661d  ldc.i4.2
0x661e  ldstr    aAndLookupentit_0// "' and LookupEntityName='"
0x6623  stelem.ref
0x6624  dup
0x6625  ldc.i4.3
0x6626  ldarg.2
0x6627  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x662c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x6631  stelem.ref
0x6632  dup
0x6633  ldc.i4.4
0x6634  ldstr    asc_E1E0// "']"
0x6639  stelem.ref
0x663a  call     string [mscorlib]System.String::Concat(string[])
0x663f  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x6644  stloc.s  7
0x6646  ldloc.s  7
0x6648  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x664d  stloc.3
0x664e  br.s     loc_6670
0x6650  ldloc.3
0x6651  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6656  castclass [System.Xml]System.Xml.XmlNode
0x665b  ldstr    aLookupattribut// "LookupAttributeName"
0x6660  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x6665  ldarg.2
0x6666  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x666b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x6670  ldloc.3
0x6671  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6676  brtrue.s loc_6650
0x6678  leave.s  loc_669A
0x667a  ldloc.3
0x667b  isinst   [mscorlib]System.IDisposable
0x6680  stloc.s  6
0x6682  ldloc.s  6
0x6684  brfalse.s loc_668D
0x6686  ldloc.s  6
0x6688  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x668d  endfinally
0x668e  ldloc.s  7
0x6690  brfalse.s loc_6699
0x6692  ldloc.s  7
0x6694  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6699  endfinally
0x669a  ldarg.1
0x669b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x66a0  ldarg.1
0x66a1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x66a6  pop
0x66a7  ret
```
