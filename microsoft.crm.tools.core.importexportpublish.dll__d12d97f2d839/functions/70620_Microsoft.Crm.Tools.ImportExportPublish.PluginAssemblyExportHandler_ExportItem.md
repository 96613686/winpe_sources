# Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyExportHandler::ExportItem

- ea: `0x70620`
- end: `0x70ac5`
- name: `Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyExportHandler::ExportItem`
- size: `1189`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x391e0`
- `0x39770`
- `0x39930`
- `0x39cd0`
- `0x3a5e0`
- `0x3b380`
- `0x3b3c0`
- `0x70620`
- `0x70ad0`
- `0x70ba0`

## string_xrefs

- `0x70762`: `PluginAssemblyId`
- `0x7063e`: `PluginAssembly`
- `0x7064f`: `PluginAssembly`
- `0x706e5`: `PluginAssembly`
- `0x70726`: `publickeytoken`
- `0x706a4`: `pluginassemblyid`
- `0x70772`: `pluginassemblyid`
- `0x707da`: `pluginassemblyid`
- `0x7093b`: `PluginTypeId`
- `0x708d5`: `PluginType`
- `0x7094b`: `plugintypeid`
- `0x707a5`: `PluginAssemblyAttributes`
- `0x70859`: `PluginAssemblyProperties`
- `0x7097e`: `PluginTypeAttributes`
- `0x70993`: `PluginTypeProperties`
- `0x70633`: `SolutionPluginAssemblies`
- `0x708ac`: `PluginTypes`

## pseudocode

```c

```

## disassembly

```asm
0x70620  ldarg.0
0x70621  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyExportHandler::_solutionComponentSet
0x70626  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x7062b  ldc.i4.0
0x7062c  bgt.s    loc_7062F
0x7062e  ret
0x7062f  nop
0x70630  ldc.i4.0
0x70631  stloc.0
0x70632  ldarg.1
0x70633  ldstr    aSolutionplugin// "SolutionPluginAssemblies"
0x70638  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x7063d  stloc.1
0x7063e  ldstr    aPluginassembly_0// "PluginAssembly"
0x70643  ldarg.0
0x70644  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyExportHandler::_context
0x70649  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7064e  stloc.2
0x7064f  ldstr    aPluginassembly_0// "PluginAssembly"
0x70654  ldarg.0
0x70655  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyExportHandler::_context
0x7065a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x7065f  stloc.3
0x70660  ldloc.3
0x70661  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x70666  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x7066b  ldloc.2
0x7066c  ldloc.3
0x7066d  ldarg.0
0x7066e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyExportHandler::_context
0x70673  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x70678  newobj   instance void class [System]System.Collections.Generic.SortedDictionary`2<string, class [System.Xml]System.Xml.XmlNode>::.ctor()
0x7067d  stloc.s  4
0x7067f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x70684  stloc.s  5
0x70686  br       loc_70A2D
0x7068b  ldloc.s  5
0x7068d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x70692  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x70697  stloc.s  6
0x70699  ldc.i4.0
0x7069a  stloc.s  7
0x7069c  ldarg.0
0x7069d  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyExportHandler::_solutionComponentSet
0x706a2  ldloc.s  6
0x706a4  ldstr    aPluginassembly_1// "pluginassemblyid"
0x706a9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x706ae  unbox.any [mscorlib]System.Guid
0x706b3  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x706b8  brfalse  loc_70A2D
0x706bd  ldloc.s  6
0x706bf  ldstr    aIshidden_0// "ishidden"
0x706c4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x706c9  unbox.any [mscorlib]System.Boolean
0x706ce  brtrue   loc_70A2D
0x706d3  ldloc.s  6
0x706d5  ldstr    aName// "name"
0x706da  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x706df  isinst   [mscorlib]System.String
0x706e4  ldarg.1
0x706e5  ldstr    aPluginassembly_0// "PluginAssembly"
0x706ea  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x706ef  stloc.s  8
0x706f1  ldarg.1
0x706f2  ldstr    aFullname// "FullName"
0x706f7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x706fc  stloc.s  9
0x706fe  ldloc.s  6
0x70700  ldstr    aVersion// "version"
0x70705  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7070a  isinst   [mscorlib]System.String
0x7070f  stloc.s  0xA
0x70711  ldloc.s  6
0x70713  ldstr    aCulture// "culture"
0x70718  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7071d  isinst   [mscorlib]System.String
0x70722  stloc.s  0xB
0x70724  ldloc.s  6
0x70726  ldstr    aPublickeytoken// "publickeytoken"
0x7072b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x70730  isinst   [mscorlib]System.String
0x70735  stloc.s  0xC
0x70737  ldloc.s  0xA
0x70739  ldloc.s  0xB
0x7073b  ldloc.s  0xC
0x7073d  newobj   instance void [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata::.ctor(string, string, string, string)
0x70742  callvirt instance string [mscorlib]System.Object::ToString()
0x70747  stloc.s  0xD
0x70749  ldloc.s  9
0x7074b  ldloc.s  0xD
0x7074d  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x70752  ldloc.s  8
0x70754  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x70759  ldloc.s  9
0x7075b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x70760  pop
0x70761  ldarg.1
0x70762  ldstr    aPluginassembly// "PluginAssemblyId"
0x70767  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x7076c  stloc.s  0xE
0x7076e  ldloc.s  0xE
0x70770  ldloc.s  6
0x70772  ldstr    aPluginassembly_1// "pluginassemblyid"
0x70777  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7077c  unbox.any [mscorlib]System.Guid
0x70781  stloc.s  0x11
0x70783  ldloca.s 0x11
0x70785  constrained. [mscorlib]System.Guid
0x7078b  callvirt instance string [mscorlib]System.Object::ToString()
0x70790  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x70795  ldloc.s  8
0x70797  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x7079c  ldloc.s  0xE
0x7079e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x707a3  pop
0x707a4  ldarg.0
0x707a5  ldstr    aPluginassembly_2// "PluginAssemblyAttributes"
0x707aa  ldarg.1
0x707ab  ldloc.s  8
0x707ad  ldloc.s  6
0x707af  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x707b4  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributes(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container)
0x707b9  ldloc.s  6
0x707bb  ldstr    aSolutionid// "solutionid"
0x707c0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x707c5  unbox.any [mscorlib]System.Guid
0x707ca  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x707cf  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x707d4  stloc.s  0xF
0x707d6  ldarg.0
0x707d7  ldloc.2
0x707d8  ldloc.s  6
0x707da  ldstr    aPluginassembly_1// "pluginassemblyid"
0x707df  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x707e4  unbox.any [mscorlib]System.Guid
0x707e9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyExportHandler::GetPluginTypes(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject bpo, valuetype [mscorlib]System.Guid pluginAssemblyId)
0x707ee  stloc.s  0x10
0x707f0  ldloc.s  0x10
0x707f2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x707f7  stloc.s  0x12
0x707f9  br.s     loc_70829
0x707fb  ldloc.s  0x12
0x707fd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x70802  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x70807  stloc.s  0x13
0x70809  ldloc.s  0xF
0x7080b  ldloc.s  0x13
0x7080d  ldstr    aSolutionid// "solutionid"
0x70812  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x70817  unbox.any [mscorlib]System.Guid
0x7081c  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x70821  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x70826  or
0x70827  stloc.s  0xF
0x70829  ldloc.s  0x12
0x7082b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x70830  brtrue.s loc_707FB
0x70832  leave.s  loc_70849
0x70834  ldloc.s  0x12
0x70836  isinst   [mscorlib]System.IDisposable
0x7083b  stloc.s  0x14
0x7083d  ldloc.s  0x14
0x7083f  brfalse.s loc_70848
0x70841  ldloc.s  0x14
0x70843  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x70848  endfinally
0x70849  ldloc.s  0xF
0x7084b  brtrue.s loc_70858
0x7084d  ldarg.0
0x7084e  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::_exportDeltaOverride
0x70853  brfalse  loc_709E3
0x70858  ldarg.0
0x70859  ldstr    aPluginassembly_3// "PluginAssemblyProperties"
0x7085e  ldarg.1
0x7085f  ldloc.s  8
0x70861  ldloc.s  6
0x70863  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x70868  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container)
0x7086d  ldloc.s  6
0x7086f  ldstr    aSourcetype// "sourcetype"
0x70874  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x70879  unbox.any [mscorlib]System.Int32
0x7087e  ldc.i4.3
0x7087f  bne.un.s loc_708A0
0x70881  ldarg.0
0x70882  ldarg.1
0x70883  ldloc.s  8
0x70885  ldstr    aAuthtype// "AuthType"
0x7088a  ldloc.s  6
0x7088c  ldstr    aAuthtype_0// "authtype"
0x70891  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x70896  callvirt instance string [mscorlib]System.Object::ToString()
0x7089b  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, string nodeName, string value)
0x708a0  ldarg.0
0x708a1  ldloc.s  6
0x708a3  ldloc.s  8
0x708a5  ldarg.1
0x708a6  call     instance void Microsoft.Crm.Tools.ImportExportPublish.PluginAssemblyExportHandler::ExportFile(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [System.Xml]System.Xml.XmlNode node, class [System.Xml]System.Xml.XmlDocument doc)
0x708ab  ldarg.1
0x708ac  ldstr    aPlugintypes// "PluginTypes"
0x708b1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x708b6  stloc.s  0x15
0x708b8  ldloc.s  0x10
0x708ba  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x708bf  stloc.s  0x12
0x708c1  br       loc_709B1
0x708c6  ldloc.s  0x12
0x708c8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x708cd  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x708d2  stloc.s  0x16
0x708d4  ldarg.1
0x708d5  ldstr    aPlugintype// "PluginType"
0x708da  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x708df  stloc.s  0x17
0x708e1  ldarg.1
0x708e2  ldstr    aAssemblyqualif// "AssemblyQualifiedName"
0x708e7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x708ec  stloc.s  0x18
0x708ee  ldloc.s  0x16
0x708f0  ldstr    aTypename// "typename"
0x708f5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x708fa  isinst   [mscorlib]System.String
0x708ff  stloc.s  0x19
0x70901  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x70906  ldstr    a01_0// "{0}, {1}"
0x7090b  ldc.i4.2
0x7090c  newarr   [mscorlib]System.Object
0x70911  dup
0x70912  ldc.i4.0
0x70913  ldloc.s  0x19
0x70915  stelem.ref
0x70916  dup
0x70917  ldc.i4.1
0x70918  ldloc.s  0xD
0x7091a  stelem.ref
0x7091b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x70920  stloc.s  0x1A
0x70922  ldloc.s  0x18
0x70924  ldloc.s  0x1A
0x70926  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x7092b  ldloc.s  0x17
0x7092d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x70932  ldloc.s  0x18
0x70934  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x70939  pop
0x7093a  ldarg.1
0x7093b  ldstr    aPlugintypeid// "PluginTypeId"
0x70940  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x70945  stloc.s  0x1B
0x70947  ldloc.s  0x1B
0x70949  ldloc.s  0x16
0x7094b  ldstr    aPlugintypeid_0// "plugintypeid"
0x70950  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x70955  unbox.any [mscorlib]System.Guid
0x7095a  stloc.s  0x11
0x7095c  ldloca.s 0x11
0x7095e  constrained. [mscorlib]System.Guid
0x70964  callvirt instance string [mscorlib]System.Object::ToString()
0x70969  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x7096e  ldloc.s  0x17
0x70970  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x70975  ldloc.s  0x1B
0x70977  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x7097c  pop
0x7097d  ldarg.0
0x7097e  ldstr    aPlugintypeattr// "PluginTypeAttributes"
0x70983  ldarg.1
0x70984  ldloc.s  0x17
0x70986  ldloc.s  0x16
0x70988  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x7098d  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlAttributes(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container)
0x70992  ldarg.0
0x70993  ldstr    aPlugintypeprop// "PluginTypeProperties"
0x70998  ldarg.1
0x70999  ldloc.s  0x17
0x7099b  ldloc.s  0x16
0x7099d  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.GenericTypeBusinessEntity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity be)
0x709a2  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ExportHandler::AddXmlProperties(string itemType, class [System.Xml]System.Xml.XmlDocument importDocument, class [System.Xml]System.Xml.XmlNode parentNode, class Microsoft.Crm.Tools.ImportExportPublish.GenericType container)
0x709a7  ldloc.s  0x15
0x709a9  ldloc.s  0x17
0x709ab  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x709b0  pop
0x709b1  ldloc.s  0x12
0x709b3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x709b8  brtrue   loc_708C6
0x709bd  leave.s  loc_709D4
0x709bf  ldloc.s  0x12
0x709c1  isinst   [mscorlib]System.IDisposable
0x709c6  stloc.s  0x14
0x709c8  ldloc.s  0x14
0x709ca  brfalse.s loc_709D3
0x709cc  ldloc.s  0x14
0x709ce  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x709d3  endfinally
0x709d4  ldloc.s  8
0x709d6  ldloc.s  0x15
0x709d8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x709dd  pop
0x709de  ldc.i4.1
0x709df  stloc.s  7
  ... truncated ...
```
