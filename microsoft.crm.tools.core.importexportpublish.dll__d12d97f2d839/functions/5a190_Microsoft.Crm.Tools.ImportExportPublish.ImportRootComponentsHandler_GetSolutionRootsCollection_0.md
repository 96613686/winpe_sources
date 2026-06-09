# Microsoft.Crm.Tools.ImportExportPublish.ImportRootComponentsHandler::GetSolutionRootsCollection_0

- ea: `0x5a190`
- end: `0x5a503`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportRootComponentsHandler::GetSolutionRootsCollection_0`
- size: `883`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x5a180`
- `0x5a510`

## callees

- `0x13090`
- `0x505c0`
- `0x508a0`
- `0x508e0`
- `0x5a190`
- `0x5a7a0`
- `0x63df0`
- `0x66d10`
- `0x686f0`

## string_xrefs

- `0x5a190`: `SolutionComponent`
- `0x5a1b1`: `SolutionManifest`
- `0x5a1de`: `RootComponents/RootComponent`
- `0x5a254`: `msdynce_Service`

## pseudocode

```c

```

## disassembly

```asm
0x5a190  ldstr    aSolutioncompon// "SolutionComponent"
0x5a195  ldarg.0
0x5a196  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRootComponentsHandler::context
0x5a19b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5a1a0  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x5a1a5  stloc.0
0x5a1a6  ldarg.0
0x5a1a7  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x5a1ac  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x5a1b1  ldstr    aSolutionmanife_2// "SolutionManifest"
0x5a1b6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5a1bb  stloc.1
0x5a1bc  ldloc.1
0x5a1bd  brtrue.s loc_5A1C1
0x5a1bf  ldloc.0
0x5a1c0  ret
0x5a1c1  ldsfld   string [mscorlib]System.String::Empty
0x5a1c6  stloc.2
0x5a1c7  ldloc.1
0x5a1c8  ldstr    aUniquename_1// "./UniqueName"
0x5a1cd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5a1d2  stloc.3
0x5a1d3  ldloc.3
0x5a1d4  brfalse.s loc_5A1DD
0x5a1d6  ldloc.3
0x5a1d7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5a1dc  stloc.2
0x5a1dd  ldloc.1
0x5a1de  ldstr    aRootcomponents_1// "RootComponents/RootComponent"
0x5a1e3  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x5a1e8  stloc.s  4
0x5a1ea  ldarg.0
0x5a1eb  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Parent()
0x5a1f0  brfalse.s loc_5A204
0x5a1f2  ldarg.0
0x5a1f3  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Parent()
0x5a1f8  ldloc.s  4
0x5a1fa  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x5a1ff  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::set_ComponentCount(int32 value)
0x5a204  ldloc.s  4
0x5a206  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5a20b  stloc.s  5
0x5a20d  br       loc_5A4D2
0x5a212  ldloc.s  5
0x5a214  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5a219  castclass [System.Xml]System.Xml.XmlNode
0x5a21e  stloc.s  6
0x5a220  ldloc.s  6
0x5a222  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5a227  ldstr    aType_0// "type"
0x5a22c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x5a231  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5a236  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a23b  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x5a240  stloc.s  7
0x5a242  ldarg.2
0x5a243  brfalse.s loc_5A24E
0x5a245  ldloc.s  7
0x5a247  ldc.i4.s 0x32
0x5a249  beq      loc_5A4D2
0x5a24e  ldloc.s  7
0x5a250  ldc.i4.s 0x25
0x5a252  bne.un.s loc_5A265
0x5a254  ldstr    aMsdynceService// "msdynce_Service"
0x5a259  ldloc.2
0x5a25a  ldc.i4.5
0x5a25b  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x5a260  brtrue   loc_5A4D2
0x5a265  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5a26a  stloc.s  8
0x5a26c  ldsfld   string [mscorlib]System.String::Empty
0x5a271  stloc.s  9
0x5a273  ldc.i4.0
0x5a274  stloc.s  0xA
0x5a276  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5a27b  stloc.s  0xB
0x5a27d  ldloc.s  6
0x5a27f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5a284  ldstr    aId// "id"
0x5a289  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x5a28e  brfalse.s loc_5A2B7
0x5a290  ldloca.s 8
0x5a292  ldloc.s  6
0x5a294  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5a299  ldstr    aId// "id"
0x5a29e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x5a2a3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5a2a8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a2ad  callvirt instance string [mscorlib]System.String::ToString(class [mscorlib]System.IFormatProvider)
0x5a2b2  call     instance void [mscorlib]System.Guid::.ctor(string)
0x5a2b7  ldloc.s  6
0x5a2b9  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5a2be  ldstr    aSchemaname_1// "schemaName"
0x5a2c3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x5a2c8  brfalse.s loc_5A2E2
0x5a2ca  ldloc.s  6
0x5a2cc  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5a2d1  ldstr    aSchemaname_1// "schemaName"
0x5a2d6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x5a2db  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5a2e0  stloc.s  9
0x5a2e2  ldloc.s  6
0x5a2e4  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5a2e9  ldstr    aParentid// "parentId"
0x5a2ee  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x5a2f3  brfalse.s loc_5A31C
0x5a2f5  ldloca.s 0xB
0x5a2f7  ldloc.s  6
0x5a2f9  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5a2fe  ldstr    aParentid// "parentId"
0x5a303  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x5a308  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5a30d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a312  callvirt instance string [mscorlib]System.String::ToString(class [mscorlib]System.IFormatProvider)
0x5a317  call     instance void [mscorlib]System.Guid::.ctor(string)
0x5a31c  ldloc.s  6
0x5a31e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5a323  ldstr    aBehavior// "behavior"
0x5a328  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x5a32d  brfalse.s loc_5A351
0x5a32f  ldloc.s  6
0x5a331  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5a336  ldstr    aBehavior// "behavior"
0x5a33b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x5a340  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5a345  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a34a  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x5a34f  stloc.s  0xA
0x5a351  ldloc.s  7
0x5a353  ldloc.s  8
0x5a355  ldloc.s  0xB
0x5a357  ldc.i4.0
0x5a358  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::.ctor(int32, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32)
0x5a35d  stloc.s  0xC
0x5a35f  ldloc.s  0xC
0x5a361  ldloc.s  9
0x5a363  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::set_SchemaName(string)
0x5a368  ldloc.s  7
0x5a36a  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0x5a36f  ldloc.s  0xC
0x5a371  ldarg.0
0x5a372  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRootComponentsHandler::context
0x5a377  callvirt instance bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::TryResolveComponentPrimaryKey(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5a37c  brfalse.s loc_5A3D8
0x5a37e  ldloc.s  7
0x5a380  ldc.i4.s 0x5C
0x5a382  bne.un.s loc_5A3AD
0x5a384  ldarg.0
0x5a385  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRootComponentsHandler::context
0x5a38a  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SolutionsHelper::IsInternalSolution(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5a38f  brtrue.s loc_5A3AD
0x5a391  ldstr    aSdkmessageproc// "SdkMessageProcessingStep"
0x5a396  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.HiddenComponentRootFilter::.ctor(string)
0x5a39b  ldloc.s  8
0x5a39d  ldarg.0
0x5a39e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRootComponentsHandler::context
0x5a3a3  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.RootFilterBase::IsRoot(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5a3a8  brfalse  loc_5A4D2
0x5a3ad  ldloc.s  0xC
0x5a3af  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ObjectId()
0x5a3b4  box      [mscorlib]System.Guid
0x5a3b9  ldloc.s  7
0x5a3bb  ldloc.s  0xA
0x5a3bd  ldarg.0
0x5a3be  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportRootComponentsHandler::context
0x5a3c3  call     class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent Microsoft.Crm.Tools.ImportExportPublish.Helper::PrepareSolutionComponent(object objectId, int32 componentType, int32 rootComponentBehavior, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5a3c8  stloc.s  0xD
0x5a3ca  ldloc.0
0x5a3cb  ldloc.s  0xD
0x5a3cd  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x5a3d2  pop
0x5a3d3  br       loc_5A4D2
0x5a3d8  ldarg.1
0x5a3d9  brfalse  loc_5A4D2
0x5a3de  ldarg.0
0x5a3df  ldarg.0
0x5a3e0  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x5a3e5  ldloc.s  0xC
0x5a3e7  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportRootComponentsHandler::IsExcluded(class [System.Xml]System.Xml.XmlDocument importXmlDocument, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo cInfo)
0x5a3ec  brtrue   loc_5A4D2
0x5a3f1  ldarg.0
0x5a3f2  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportRootComponentsHandler::tracer
0x5a3f7  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::RootComponentsImportErrorMessage
0x5a3fc  ldnull
0x5a3fd  ldc.i4.3
0x5a3fe  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x5a403  ldc.i4.2
0x5a404  newarr   [mscorlib]System.String
0x5a409  stloc.s  0xE
0x5a40b  ldloc.s  0xE
0x5a40d  ldc.i4.0
0x5a40e  ldloc.s  0xC
0x5a410  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_SchemaName()
0x5a415  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a41a  brtrue.s loc_5A425
0x5a41c  ldloc.s  0xC
0x5a41e  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_SchemaName()
0x5a423  br.s     loc_5A43B
0x5a425  ldloc.s  0xC
0x5a427  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ObjectId()
0x5a42c  stloc.s  0x10
0x5a42e  ldloca.s 0x10
0x5a430  constrained. [mscorlib]System.Guid
0x5a436  callvirt instance string [mscorlib]System.Object::ToString()
0x5a43b  stelem.ref
0x5a43c  ldloc.s  0xE
0x5a43e  ldc.i4.1
0x5a43f  ldloc.s  7
0x5a441  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5a446  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x5a44b  stelem.ref
0x5a44c  ldc.i4   0x8004801F
0x5a451  ldloc.s  0xE
0x5a453  stloc.s  0x11
0x5a455  ldloc.s  0x11
0x5a457  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x5a45c  stloc.s  0xF
0x5a45e  ldloc.s  0xC
0x5a460  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_SchemaName()
0x5a465  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a46a  brtrue.s loc_5A494
0x5a46c  ldarg.0
0x5a46d  ldloc.s  7
0x5a46f  ldloc.s  8
0x5a471  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::IsComponentToBeSkipped(int32 type, valuetype [mscorlib]System.Guid id)
0x5a476  brfalse.s loc_5A494
0x5a478  ldarg.0
0x5a479  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Parent()
0x5a47e  ldarg.0
0x5a47f  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x5a484  ldstr    aWarning// "warning"
0x5a489  ldloc.s  0xF
0x5a48b  ldc.i4.1
0x5a48c  ldc.i4.0
0x5a48d  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x5a492  br.s     loc_5A4D2
0x5a494  ldloc.s  0xC
0x5a496  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ObjectId()
0x5a49b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5a4a0  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5a4a5  brfalse.s loc_5A4CF
0x5a4a7  ldarg.0
0x5a4a8  ldloc.s  7
0x5a4aa  ldloc.s  8
0x5a4ac  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::IsComponentToBeSkipped(int32 type, valuetype [mscorlib]System.Guid id)
0x5a4b1  brfalse.s loc_5A4CF
0x5a4b3  ldarg.0
0x5a4b4  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_Parent()
0x5a4b9  ldarg.0
0x5a4ba  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x5a4bf  ldstr    aWarning// "warning"
0x5a4c4  ldloc.s  0xF
0x5a4c6  ldc.i4.1
0x5a4c7  ldc.i4.0
0x5a4c8  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x5a4cd  br.s     loc_5A4D2
0x5a4cf  ldloc.s  0xF
0x5a4d1  throw
0x5a4d2  ldloc.s  5
0x5a4d4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5a4d9  brtrue   loc_5A212
0x5a4de  leave.s  loc_5A501
0x5a4e0  ldloc.s  5
0x5a4e2  isinst   [mscorlib]System.IDisposable
0x5a4e7  stloc.s  0x12
0x5a4e9  ldloc.s  0x12
0x5a4eb  brfalse.s loc_5A4F4
0x5a4ed  ldloc.s  0x12
0x5a4ef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a4f4  endfinally
0x5a4f5  ldloc.s  4
0x5a4f7  brfalse.s loc_5A500
0x5a4f9  ldloc.s  4
0x5a4fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a500  endfinally
0x5a501  ldloc.0
0x5a502  ret
```
