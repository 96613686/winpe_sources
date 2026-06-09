# Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::ImportItem

- ea: `0x3d1c0`
- end: `0x3d5e7`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::ImportItem`
- size: `1063`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x27f20`
- `0x27fa0`
- `0x28f50`
- `0x28fc0`
- `0x28fd0`
- `0x366a0`
- `0x3d1c0`
- `0x3d5f0`
- `0x3d690`
- `0x3d700`
- `0x4cd50`
- `0x508e0`
- `0x63db0`
- `0x63df0`
- `0x686f0`
- `0x7bc70`

## string_xrefs

- `0x3d349`: `AppConfig`
- `0x3d379`: `AppConfig`
- `0x3d4ba`: `AppConfig`
- `0x3d1e4`: `ImportAppModulesHandler.ImportItem(): AppModule XMLNode [{0}] not present.`
- `0x3d2f5`: `ImportAppModulesHandler.ImportItem(): Installed AppModule with [appmoduleid:{0}]`
- `0x3d4ab`: `ImportAppModulesHandler.ImportItem(): AppConfig Exists {0}`
- `0x3d4df`: `ImportAppModulesHandler.ImportItem(): FCB AppConfigForOrganization Enabled : {0}`

## pseudocode

```c

```

## disassembly

```asm
0x3d1c0  ldarg.0
0x3d1c1  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x3d1c6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x3d1cb  ldstr    aAppmodules// "AppModules"
0x3d1d0  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d1d5  brtrue.s loc_3D1FD
0x3d1d7  ldarg.0
0x3d1d8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_context
0x3d1dd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3d1e2  ldc.i4.s 0x47
0x3d1e4  ldstr    aImportappmodul_0// "ImportAppModulesHandler.ImportItem(): A"...
0x3d1e9  ldc.i4.1
0x3d1ea  newarr   [mscorlib]System.Object
0x3d1ef  dup
0x3d1f0  ldc.i4.0
0x3d1f1  ldstr    aAppmodules// "AppModules"
0x3d1f6  stelem.ref
0x3d1f7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3d1fc  ret
0x3d1fd  ldarg.0
0x3d1fe  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_context
0x3d203  ldarg.0
0x3d204  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_tracer
0x3d209  ldarg.0
0x3d20a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_context
0x3d20f  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportExportUtils::GetRoleTemplateIdToRoleIdMap(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x3d214  ldarg.0
0x3d215  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::get_AllRoleIds()
0x3d21a  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> roleTemplateIdToRoleIdMap, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> allRoleIds)
0x3d21f  stloc.0
0x3d220  ldarg.0
0x3d221  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_context
0x3d226  ldarg.0
0x3d227  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_tracer
0x3d22c  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer tracer)
0x3d231  stloc.1
0x3d232  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3d237  stloc.2
0x3d238  ldarg.0
0x3d239  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x3d23e  call     bool Microsoft.Crm.Tools.ImportExportPublish.RootImportHandler::IsManagedSolutionInDocument(class [System.Xml]System.Xml.XmlDocument xmlDocument)
0x3d243  stloc.3
0x3d244  ldarg.0
0x3d245  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x3d24a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x3d24f  ldstr    aAppmodules// "AppModules"
0x3d254  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d259  ldstr    aAppmodule// "AppModule"
0x3d25e  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x3d263  stloc.s  4
0x3d265  ldarg.0
0x3d266  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_context
0x3d26b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3d270  ldc.i4.s 0x47
0x3d272  ldstr    aImportappmodul_1// "ImportAppModulesHandler.ImportItem(): ["...
0x3d277  ldc.i4.2
0x3d278  newarr   [mscorlib]System.Object
0x3d27d  dup
0x3d27e  ldc.i4.0
0x3d27f  ldstr    aAppmodules// "AppModules"
0x3d284  stelem.ref
0x3d285  dup
0x3d286  ldc.i4.1
0x3d287  ldloc.s  4
0x3d289  brtrue.s loc_3D297
0x3d28b  ldloca.s 5
0x3d28d  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3d293  ldloc.s  5
0x3d295  br.s     loc_3D2A3
0x3d297  ldloc.s  4
0x3d299  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x3d29e  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x3d2a3  box      valuetype [mscorlib]System.Nullable`1<int32>
0x3d2a8  stelem.ref
0x3d2a9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3d2ae  ldloc.s  4
0x3d2b0  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x3d2b5  stloc.s  6
0x3d2b7  br       loc_3D558
0x3d2bc  ldloc.s  6
0x3d2be  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3d2c3  castclass [System.Xml]System.Xml.XmlNode
0x3d2c8  stloc.s  7
0x3d2ca  ldarg.0
0x3d2cb  ldloc.s  7
0x3d2cd  stfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::appModuleNodeCurrent
0x3d2d2  ldloc.0
0x3d2d3  ldarg.0
0x3d2d4  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::appModuleNodeCurrent
0x3d2d9  ldarg.0
0x3d2da  ldloc.s  7
0x3d2dc  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::GetLocalizedColumnsValues(class [System.Xml]System.Xml.XmlNode appModuleNode)
0x3d2e1  ldloc.3
0x3d2e2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.AppModulesInstaller::Install(class [System.Xml]System.Xml.XmlNode appModuleNode, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> localizedColumnValuePair, bool isManagedSolution)
0x3d2e7  stloc.2
0x3d2e8  ldarg.0
0x3d2e9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_context
0x3d2ee  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3d2f3  ldc.i4.s 0x47
0x3d2f5  ldstr    aImportappmodul_2// "ImportAppModulesHandler.ImportItem(): I"...
0x3d2fa  ldc.i4.1
0x3d2fb  newarr   [mscorlib]System.Object
0x3d300  dup
0x3d301  ldc.i4.0
0x3d302  ldloc.2
0x3d303  box      [mscorlib]System.Guid
0x3d308  stelem.ref
0x3d309  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3d30e  ldarg.0
0x3d30f  ldloc.2
0x3d310  ldarg.0
0x3d311  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::appModuleNodeCurrent
0x3d316  ldstr    aAppmodule// "AppModule"
0x3d31b  ldarg.0
0x3d31c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_context
0x3d321  ldarg.0
0x3d322  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_context
0x3d327  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3d32c  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleService::.ctor()
0x3d331  newobj   instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject)
0x3d336  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::GetLabelColumnNameNodePluralNameMap()
0x3d33b  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::GetNodePluralNameSingularNameMap()
0x3d340  ldc.i4.s 0x18
0x3d342  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::ImportLocalizedLabels(valuetype [mscorlib]System.Guid appModuleId, class [System.Xml]System.Xml.XmlNode appModuleNode, string platformName, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> labelColumnNameNodePluralNameMap, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> nodePluralNameSingularNameMap, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode)
0x3d347  ldloc.s  7
0x3d349  ldstr    aAppconfig// "AppConfig"
0x3d34e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d353  brfalse  loc_3D49E
0x3d358  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x3d35d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x3d362  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AppConfigForOrganization()
0x3d367  ldarg.0
0x3d368  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_context
0x3d36d  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3d372  brfalse  loc_3D49E
0x3d377  ldloc.s  7
0x3d379  ldstr    aAppconfig// "AppConfig"
0x3d37e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d383  stloc.s  9
0x3d385  ldloc.s  9
0x3d387  ldstr    aNavigationsett// "NavigationSettings"
0x3d38c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3d391  ldstr    aNavigationsett_0// "NavigationSetting"
0x3d396  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x3d39b  stloc.s  0xA
0x3d39d  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>>::.ctor()
0x3d3a2  stloc.s  0xB
0x3d3a4  ldloc.s  0xA
0x3d3a6  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x3d3ab  stloc.s  0xC
0x3d3ad  br.s     loc_3D3DD
0x3d3af  ldloc.s  0xC
0x3d3b1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3d3b6  castclass [System.Xml]System.Xml.XmlNode
0x3d3bb  stloc.s  0xD
0x3d3bd  ldloc.s  0xB
0x3d3bf  ldloc.s  0xD
0x3d3c1  ldstr    aNavigationsett_1// "NavigationSettingId"
0x3d3c6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3d3cb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3d3d0  ldarg.0
0x3d3d1  ldloc.s  0xD
0x3d3d3  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::GetLocalizedColumnsValues(class [System.Xml]System.Xml.XmlNode appModuleNode)
0x3d3d8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>>::Add(var<u1>, !!T0)
0x3d3dd  ldloc.s  0xC
0x3d3df  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3d3e4  brtrue.s loc_3D3AF
0x3d3e6  leave.s  loc_3D3FD
0x3d3e8  ldloc.s  0xC
0x3d3ea  isinst   [mscorlib]System.IDisposable
0x3d3ef  stloc.s  0xE
0x3d3f1  ldloc.s  0xE
0x3d3f3  brfalse.s loc_3D3FC
0x3d3f5  ldloc.s  0xE
0x3d3f7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3d3fc  endfinally
0x3d3fd  ldloc.1
0x3d3fe  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::GetAppConfigUtility()
0x3d403  ldloc.s  0xB
0x3d405  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::SetNavSettingsLocalizedColumnValuePairList(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>>)
0x3d40a  ldloc.1
0x3d40b  ldloc.s  9
0x3d40d  ldloc.3
0x3d40e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::Install(class [System.Xml]System.Xml.XmlNode appConfigNode, bool isManagedSolution)
0x3d413  pop
0x3d414  ldloc.s  0xA
0x3d416  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x3d41b  stloc.s  0xC
0x3d41d  br.s     loc_3D47B
0x3d41f  ldloc.s  0xC
0x3d421  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x3d426  castclass [System.Xml]System.Xml.XmlNode
0x3d42b  stloc.s  0xF
0x3d42d  ldloca.s 0x10
0x3d42f  ldloc.s  0xF
0x3d431  ldstr    aNavigationsett_1// "NavigationSettingId"
0x3d436  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x3d43b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3d440  call     instance void [mscorlib]System.Guid::.ctor(string)
0x3d445  ldarg.0
0x3d446  ldloc.s  0x10
0x3d448  ldloc.s  0xF
0x3d44a  ldstr    aNavigationsett_0// "NavigationSetting"
0x3d44f  ldarg.0
0x3d450  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_context
0x3d455  ldarg.0
0x3d456  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_context
0x3d45b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3d460  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.NavigationSettingService::.ctor()
0x3d465  newobj   instance void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject)
0x3d46a  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::GetLabelColumnNameNodePluralNameMap()
0x3d46f  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::GetNodePluralNameSingularNameMap()
0x3d474  ldc.i4.s 0x1C
0x3d476  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::ImportLocalizedLabels(valuetype [mscorlib]System.Guid appModuleId, class [System.Xml]System.Xml.XmlNode appModuleNode, string platformName, class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper metadataHelper, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> labelColumnNameNodePluralNameMap, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> nodePluralNameSingularNameMap, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelTypeCode labelTypeCode)
0x3d47b  ldloc.s  0xC
0x3d47d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3d482  brtrue.s loc_3D41F
0x3d484  leave    loc_3D511
0x3d489  ldloc.s  0xC
0x3d48b  isinst   [mscorlib]System.IDisposable
0x3d490  stloc.s  0xE
0x3d492  ldloc.s  0xE
0x3d494  brfalse.s loc_3D49D
0x3d496  ldloc.s  0xE
0x3d498  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3d49d  endfinally
0x3d49e  ldarg.0
0x3d49f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_context
0x3d4a4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3d4a9  ldc.i4.s 0x47
0x3d4ab  ldstr    aImportappmodul_3// "ImportAppModulesHandler.ImportItem(): A"...
0x3d4b0  ldc.i4.1
0x3d4b1  newarr   [mscorlib]System.Object
0x3d4b6  dup
0x3d4b7  ldc.i4.0
0x3d4b8  ldloc.s  7
0x3d4ba  ldstr    aAppconfig// "AppConfig"
0x3d4bf  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3d4c4  ldnull
0x3d4c5  ceq
0x3d4c7  box      [mscorlib]System.Boolean
0x3d4cc  stelem.ref
0x3d4cd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3d4d2  ldarg.0
0x3d4d3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_context
0x3d4d8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x3d4dd  ldc.i4.s 0x47
0x3d4df  ldstr    aImportappmodul_4// "ImportAppModulesHandler.ImportItem(): F"...
0x3d4e4  ldc.i4.1
0x3d4e5  newarr   [mscorlib]System.Object
0x3d4ea  dup
0x3d4eb  ldc.i4.0
0x3d4ec  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x3d4f1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x3d4f6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AppConfigForOrganization()
0x3d4fb  ldarg.0
0x3d4fc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_context
0x3d501  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3d506  box      [mscorlib]System.Boolean
0x3d50b  stelem.ref
0x3d50c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3d511  ldarg.0
0x3d512  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportAppModulesHandler::_tracer
0x3d517  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3d51c  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::AppModuleImportSuccessMessage
0x3d521  ldc.i4.1
0x3d522  newarr   [mscorlib]System.Object
0x3d527  dup
0x3d528  ldc.i4.0
0x3d529  ldloc.2
0x3d52a  box      [mscorlib]System.Guid
0x3d52f  stelem.ref
0x3d530  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3d535  ldc.i4.1
0x3d536  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x3d53b  ldarg.0
0x3d53c  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::GetParameterXPath()
0x3d541  stloc.s  8
0x3d543  ldarg.0
0x3d544  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x3d549  ldloc.s  8
0x3d54b  ldstr    aSuccess// "success"
0x3d550  ldnull
0x3d551  ldc.i4.1
0x3d552  ldc.i4.0
0x3d553  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x3d558  ldloc.s  6
0x3d55a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3d55f  brtrue   loc_3D2BC
0x3d564  leave.s  loc_3D57B
0x3d566  ldloc.s  6
0x3d568  isinst   [mscorlib]System.IDisposable
0x3d56d  stloc.s  0xE
0x3d56f  ldloc.s  0xE
0x3d571  brfalse.s loc_3D57A
0x3d573  ldloc.s  0xE
0x3d575  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3d57a  endfinally
0x3d57b  leave.s  loc_3D5E6
0x3d57d  stloc.s  0x11
  ... truncated ...
```
