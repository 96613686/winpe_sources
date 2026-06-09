# Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::UpdateExistingImportMap

- ea: `0x622d0`
- end: `0x6256c`
- name: `Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::UpdateExistingImportMap`
- size: `668`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x60e70`

## callees

- `0x5be20`
- `0x5fb00`
- `0x5fb10`
- `0x5fba0`
- `0x5fc90`
- `0x61700`
- `0x61b90`
- `0x622d0`
- `0x63790`
- `0x63880`
- `0x639d0`
- `0x63b50`
- `0x66ae0`
- `0x66df0`
- `0x6a810`

## string_xrefs

- `0x62300`: `ImportMapXml given is invalid`
- `0x62305`: `existingMapXml`

## pseudocode

```c

```

## disassembly

```asm
0x622d0  ldarg.1
0x622d1  callvirt instance string Microsoft.Crm.Application.Platform.ImportWizardState::get_MapXml()
0x622d6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x622db  brfalse.s loc_622E5
0x622dd  ldarg.0
0x622de  ldarg.1
0x622df  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::GetImportMapXmlWithExistingMap(class Microsoft.Crm.Application.Platform.ImportWizardState wizardState)
0x622e4  ret
0x622e5  ldarg.1
0x622e6  callvirt instance string Microsoft.Crm.Application.Platform.ImportWizardState::get_MapXml()
0x622eb  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x622f0  stloc.0
0x622f1  ldloc.0
0x622f2  ldstr    aMapEntitymapsE_16// "/Map/EntityMaps/EntityMap[not(@Unused)]"
0x622f7  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x622fc  stloc.1
0x622fd  ldloc.1
0x622fe  brtrue.s loc_62310
0x62300  ldstr    aImportmapxmlGi// "ImportMapXml given is invalid"
0x62305  ldstr    aExistingmapxml// "existingMapXml"
0x6230a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x6230f  throw
0x62310  ldloc.0
0x62311  ldstr    aMapMapchangedT// "/Map[MapChanged=\"True\"]"
0x62316  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6231b  stloc.2
0x6231c  ldnull
0x6231d  stloc.3
0x6231e  ldstr    aImportfile// "importfile"
0x62323  ldarg.1
0x62324  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ImportWizardState::get_Context()
0x62329  call     class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Platform.EntityType::Create(string logicalName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x6232e  newobj   instance void Microsoft.Crm.Application.Platform.ImportFile::.ctor(class Microsoft.Crm.Application.Platform.EntityType type)
0x62333  ldarg.1
0x62334  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportId()
0x62339  call     instance class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.ImportFile::RetrieveImportFiles(valuetype [mscorlib]System.Guid importId)
0x6233e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Platform.Entity>::.ctor()
0x62343  stloc.s  4
0x62345  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x6234a  stloc.s  5
0x6234c  br.s     loc_62371
0x6234e  ldloc.s  5
0x62350  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x62355  stloc.s  6
0x62357  ldloc.s  4
0x62359  ldloc.s  6
0x6235b  ldstr    aSourceentityna// "sourceentityname"
0x62360  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x62365  castclass [mscorlib]System.String
0x6236a  ldloc.s  6
0x6236c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Platform.Entity>::Add(var<u1>, !!T0)
0x62371  ldloc.s  5
0x62373  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x62378  brtrue.s loc_6234E
0x6237a  leave.s  loc_62388
0x6237c  ldloc.s  5
0x6237e  brfalse.s loc_62387
0x62380  ldloc.s  5
0x62382  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x62387  endfinally
0x62388  ldloc.1
0x62389  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x6238e  stloc.s  7
0x62390  br       loc_6251F
0x62395  ldloc.s  7
0x62397  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6239c  castclass [System.Xml]System.Xml.XmlNode
0x623a1  stloc.s  8
0x623a3  ldloc.s  8
0x623a5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x623aa  ldstr    aSourceentityna_0// "SourceEntityName"
0x623af  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x623b4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x623b9  stloc.s  9
0x623bb  ldloc.s  8
0x623bd  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x623c2  ldstr    aProcesscode// "ProcessCode"
0x623c7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x623cc  brfalse  loc_6251F
0x623d1  ldloc.s  8
0x623d3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x623d8  ldstr    aProcesscode// "ProcessCode"
0x623dd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x623e2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x623e7  ldc.i4.0
0x623e8  stloc.s  0xB
0x623ea  ldloca.s 0xB
0x623ec  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x623f2  callvirt instance string [mscorlib]System.Object::ToString()
0x623f7  ldc.i4.5
0x623f8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x623fd  brfalse  loc_6251F
0x62402  ldloc.s  8
0x62404  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x62409  ldstr    aProcesscode// "ProcessCode"
0x6240e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x62413  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x62418  ldc.i4.1
0x62419  stloc.s  0xB
0x6241b  ldloca.s 0xB
0x6241d  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x62423  callvirt instance string [mscorlib]System.Object::ToString()
0x62428  ldc.i4.5
0x62429  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x6242e  brfalse  loc_6251F
0x62433  ldloc.s  8
0x62435  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6243a  ldstr    aProcesscode// "ProcessCode"
0x6243f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x62444  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x62449  ldc.i4.3
0x6244a  stloc.s  0xB
0x6244c  ldloca.s 0xB
0x6244e  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x62454  callvirt instance string [mscorlib]System.Object::ToString()
0x62459  ldc.i4.5
0x6245a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x6245f  brtrue.s loc_6249D
0x62461  ldloc.s  8
0x62463  ldstr    aAttributemaps// "AttributeMaps"
0x62468  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x6246d  brtrue.s loc_62486
0x6246f  ldarg.0
0x62470  ldloc.0
0x62471  ldloc.s  8
0x62473  ldloc.s  4
0x62475  ldloc.s  9
0x62477  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Platform.Entity>::get_Item(void)
0x6247c  call     instance void Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::MarkAllAttributesAsUnmapped(class [System.Xml]System.Xml.XmlDocument mapDoc, class [System.Xml]System.Xml.XmlNode entityNode, class Microsoft.Crm.Application.Platform.Entity importFile)
0x62481  br       loc_6251F
0x62486  ldarg.0
0x62487  ldloc.0
0x62488  ldloc.s  8
0x6248a  ldloc.s  4
0x6248c  ldloc.s  9
0x6248e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Platform.Entity>::get_Item(void)
0x62493  call     instance void Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::AddMappingsForUnmappedAttributes(class [System.Xml]System.Xml.XmlDocument mapDoc, class [System.Xml]System.Xml.XmlNode entityNode, class Microsoft.Crm.Application.Platform.Entity importFile)
0x62498  br       loc_6251F
0x6249d  ldloc.s  8
0x6249f  ldstr    aAttributemaps// "AttributeMaps"
0x624a4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x624a9  stloc.s  0xA
0x624ab  ldloc.s  0xA
0x624ad  brtrue.s loc_6250A
0x624af  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x624b4  ldarg.1
0x624b5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportMapId()
0x624ba  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x624bf  brfalse.s loc_624D4
0x624c1  ldarg.0
0x624c2  ldloc.s  8
0x624c4  ldloc.s  4
0x624c6  ldloc.s  9
0x624c8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Platform.Entity>::get_Item(void)
0x624cd  call     instance void Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::UpdateAutomappedEntityNode(class [System.Xml]System.Xml.XmlNode entityNode, class Microsoft.Crm.Application.Platform.Entity importFile)
0x624d2  br.s     loc_6251F
0x624d4  ldloc.3
0x624d5  brtrue.s loc_624EF
0x624d7  ldarg.0
0x624d8  ldarg.1
0x624d9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Platform.ImportWizardState::get_ImportMapId()
0x624de  ldarg.1
0x624df  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ImportWizardState::get_Context()
0x624e4  call     instance string Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::GetImportMapXmlFromDatabase(valuetype [mscorlib]System.Guid importMapId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x624e9  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x624ee  stloc.3
0x624ef  ldarg.0
0x624f0  ldloc.0
0x624f1  ldloc.3
0x624f2  ldloc.s  8
0x624f4  ldloc.s  4
0x624f6  ldloc.s  9
0x624f8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Platform.Entity>::get_Item(void)
0x624fd  ldarg.1
0x624fe  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ImportWizardState::get_Context()
0x62503  call     instance void Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::UpdateExisingMapEntityNode(class [System.Xml]System.Xml.XmlDocument mapDoc, class [System.Xml]System.Xml.XmlDocument dbMapDoc, class [System.Xml]System.Xml.XmlNode entityNode, class Microsoft.Crm.Application.Platform.Entity importFile, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x62508  br.s     loc_6251F
0x6250a  ldloc.2
0x6250b  brfalse.s loc_6251F
0x6250d  ldarg.0
0x6250e  ldloc.0
0x6250f  ldloc.s  8
0x62511  ldloc.s  4
0x62513  ldloc.s  9
0x62515  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Platform.Entity>::get_Item(void)
0x6251a  call     instance void Microsoft.Crm.Application.Platform.ImportMapXmlGenerator::AddMappingsForUnmappedAttributes(class [System.Xml]System.Xml.XmlDocument mapDoc, class [System.Xml]System.Xml.XmlNode entityNode, class Microsoft.Crm.Application.Platform.Entity importFile)
0x6251f  ldloc.s  7
0x62521  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x62526  brtrue   loc_62395
0x6252b  leave.s  loc_62542
0x6252d  ldloc.s  7
0x6252f  isinst   [mscorlib]System.IDisposable
0x62534  stloc.s  0xC
0x62536  ldloc.s  0xC
0x62538  brfalse.s loc_62541
0x6253a  ldloc.s  0xC
0x6253c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x62541  endfinally
0x62542  ldloc.2
0x62543  brfalse.s loc_6255E
0x62545  ldloc.2
0x62546  ldstr    aMapchanged// "MapChanged"
0x6254b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x62550  stloc.2
0x62551  ldloc.2
0x62552  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x62557  ldloc.2
0x62558  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x6255d  pop
0x6255e  leave.s  loc_6256A
0x62560  ldloc.1
0x62561  brfalse.s loc_62569
0x62563  ldloc.1
0x62564  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x62569  endfinally
0x6256a  ldloc.0
0x6256b  ret
```
