# Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::UpdateExistingPluginAssembly

- ea: `0x551b0`
- end: `0x55375`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::UpdateExistingPluginAssembly`
- size: `453`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x54950`

## callees

- `0x551b0`
- `0x55380`

## string_xrefs

- `0x55202`: `pluginassemblyid`
- `0x552b5`: `pluginassemblyid`
- `0x552c5`: `pluginassemblyid`
- `0x5528e`: `PluginType`
- `0x55233`: `ImportExportXml/SolutionManifest/Managed`

## pseudocode

```c

```

## disassembly

```asm
0x551b0  ldarg.3
0x551b1  isinst   [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PluginAssemblyService
0x551b6  stloc.0
0x551b7  ldarg.1
0x551b8  ldstr    aContent// "content"
0x551bd  ldarg.2
0x551be  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x551c3  ldarg.0
0x551c4  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_isSystemConvertedSolution
0x551c9  brfalse.s loc_551DC
0x551cb  ldarg.1
0x551cc  ldstr    aIshidden_0// "ishidden"
0x551d1  ldc.i4.1
0x551d2  box      [mscorlib]System.Boolean
0x551d7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x551dc  ldarg.1
0x551dd  ldstr    aSourcetype// "sourcetype"
0x551e2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x551e7  unbox.any [mscorlib]System.Int32
0x551ec  pop
0x551ed  ldarg.s  7
0x551ef  brfalse  loc_55374
0x551f4  ldarg.s  7
0x551f6  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x551fb  ldc.i4.0
0x551fc  ble      loc_55374
0x55201  ldarg.1
0x55202  ldstr    aPluginassembly_1// "pluginassemblyid"
0x55207  ldarg.s  7
0x55209  ldc.i4.0
0x5520a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x5520f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x55214  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x55219  ldarg.s  6
0x5521b  brfalse.s loc_5522B
0x5521d  ldloc.0
0x5521e  ldarg.1
0x5521f  ldarg.0
0x55220  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x55225  callvirt instance void class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PluginAssemblyServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.UpgradingOff>::UpdateInternalWithoutValidation(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5522a  ret
0x5522b  ldc.i4.0
0x5522c  stloc.1
0x5522d  ldarg.0
0x5522e  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x55233  ldstr    aImportexportxm_133// "ImportExportXml/SolutionManifest/Manage"...
0x55238  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x5523d  stloc.2
0x5523e  ldloc.2
0x5523f  brfalse.s loc_55255
0x55241  ldloc.2
0x55242  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x55247  ldstr    a1// "1"
0x5524c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x55251  brfalse.s loc_55255
0x55253  ldc.i4.1
0x55254  stloc.1
0x55255  ldloc.1
0x55256  brfalse  loc_55367
0x5525b  ldarg.0
0x5525c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x55261  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SolutionImportContext()
0x55266  ldc.i4.s 0x20
0x55268  beq.s    loc_5527C
0x5526a  ldarg.0
0x5526b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x55270  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionImportContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SolutionImportContext()
0x55275  ldc.i4.s 0x21
0x55277  bne.un   loc_55367
0x5527c  ldarg.0
0x5527d  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_isSystemConvertedSolution
0x55282  brtrue   loc_55367
0x55287  ldarg.s  4
0x55289  isinst   [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PluginTypeService
0x5528e  ldstr    aPlugintype// "PluginType"
0x55293  ldarg.0
0x55294  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x55299  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x5529e  stloc.3
0x5529f  ldloc.3
0x552a0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x552a5  ldstr    aTypename// "typename"
0x552aa  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x552af  ldloc.3
0x552b0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x552b5  ldstr    aPluginassembly_1// "pluginassemblyid"
0x552ba  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x552bf  ldloc.3
0x552c0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x552c5  ldstr    aPluginassembly_1// "pluginassemblyid"
0x552ca  ldc.i4.0
0x552cb  ldarg.s  7
0x552cd  ldc.i4.0
0x552ce  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x552d3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x552d8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x552dd  pop
0x552de  ldloc.3
0x552df  ldarg.0
0x552e0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x552e5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x552ea  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x552ef  stloc.s  4
0x552f1  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x552f6  stloc.s  5
0x552f8  br.s     loc_5532A
0x552fa  ldloc.s  5
0x552fc  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x55301  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x55306  stloc.s  6
0x55308  ldloc.s  4
0x5530a  ldloc.s  6
0x5530c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x55311  ldstr    aTypename// "typename"
0x55316  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x5531b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x55320  castclass [mscorlib]System.String
0x55325  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5532a  ldloc.s  5
0x5532c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x55331  brtrue.s loc_552FA
0x55333  leave.s  loc_5534A
0x55335  ldloc.s  5
0x55337  isinst   [mscorlib]System.IDisposable
0x5533c  stloc.s  7
0x5533e  ldloc.s  7
0x55340  brfalse.s loc_55349
0x55342  ldloc.s  7
0x55344  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x55349  endfinally
0x5534a  ldarg.0
0x5534b  ldarg.s  5
0x5534d  ldloc.s  4
0x5534f  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::AnyExistingPluginTypesRemoved(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginType> importingPluginTypes, class [mscorlib]System.Collections.Generic.List`1<string> existingPluginTypes)
0x55354  brfalse.s loc_55367
0x55356  ldc.i4   0x80048071
0x5535b  ldc.i4.0
0x5535c  newarr   [mscorlib]System.Object
0x55361  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x55366  throw
0x55367  ldloc.0
0x55368  ldarg.1
0x55369  ldarg.0
0x5536a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportPluginAssemblyHandler::_context
0x5536f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x55374  ret
```
