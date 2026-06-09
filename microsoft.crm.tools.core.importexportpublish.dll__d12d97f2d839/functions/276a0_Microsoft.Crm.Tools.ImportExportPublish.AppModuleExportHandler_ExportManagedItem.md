# Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::ExportManagedItem

- ea: `0x276a0`
- end: `0x27912`
- name: `Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::ExportManagedItem`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x27540`

## callees

- `0x276a0`
- `0x27a30`
- `0x27ba0`
- `0x27be0`
- `0x27ce0`
- `0x3b3c0`

## string_xrefs

- `0x276e2`: `ImportExportXml`
- `0x277c5`: `componenttype`
- `0x277ff`: `Removed`
- `0x27825`: `Removed`
- `0x27785`: `AppModuleComponent`

## pseudocode

```c

```

## disassembly

```asm
0x276a0  ldarg.0
0x276a1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::_context
0x276a6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x276ab  ldc.i4.s 0x47
0x276ad  ldstr    aAppmoduleexpor_2// "AppModuleExportHandler.ExportManagedIte"...
0x276b2  ldc.i4.0
0x276b3  newarr   [mscorlib]System.Object
0x276b8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x276bd  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleService::.ctor()
0x276c2  stloc.0
0x276c3  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleComponentService::.ctor()
0x276c8  stloc.1
0x276c9  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleRolesService::.ctor()
0x276ce  stloc.2
0x276cf  ldarg.0
0x276d0  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::_cache
0x276d5  ldarg.0
0x276d6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::_context
0x276db  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleXmlSerializer::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x276e0  stloc.3
0x276e1  ldarg.1
0x276e2  ldstr    aImportexportxm// "ImportExportXml"
0x276e7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x276ec  ldarg.1
0x276ed  ldc.i4.1
0x276ee  ldstr    aAppmodules// "AppModules"
0x276f3  ldsfld   string [mscorlib]System.String::Empty
0x276f8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x276fd  stloc.s  4
0x276ff  ldloc.s  4
0x27701  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x27706  pop
0x27707  ldarg.0
0x27708  ldloc.0
0x27709  ldloc.1
0x2770a  ldloc.2
0x2770b  call     instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition> Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::GetAppModuleDefinitions(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleService appModuleService, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleComponentService appModuleComponentService, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleRolesService appModuleRolesService)
0x27710  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition>::GetEnumerator()
0x27715  stloc.s  5
0x27717  br       loc_27896
0x2771c  ldloca.s 5
0x2771e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition>::get_Current()
0x27723  stloc.s  6
0x27725  ldnull
0x27726  stloc.s  7
0x27728  ldloc.0
0x27729  ldloc.s  6
0x2772b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_AppModuleId()
0x27730  ldarg.0
0x27731  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::_context
0x27736  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModuleService::RetrieveLastManagedAppModule(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2773b  stloc.s  8
0x2773d  ldarg.0
0x2773e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::_context
0x27743  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x27748  ldc.i4.s 0x47
0x2774a  ldstr    aAppmoduleexpor_3// "AppModuleExportHandler.ExportManagedIte"...
0x2774f  ldc.i4.1
0x27750  newarr   [mscorlib]System.Object
0x27755  dup
0x27756  ldc.i4.0
0x27757  ldloc.s  8
0x27759  brtrue.s loc_2775E
0x2775b  ldnull
0x2775c  br.s     loc_2776A
0x2775e  ldloc.s  8
0x27760  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x27765  call     instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x2776a  stelem.ref
0x2776b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x27770  ldloc.s  8
0x27772  brtrue.s loc_27785
0x27774  ldloc.3
0x27775  ldloc.s  6
0x27777  ldarg.1
0x27778  ldc.i4.0
0x27779  callvirt instance class [System.Xml]System.Xml.XmlNode [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleXmlSerializer::GetAppModuleXmlNode(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition, class [System.Xml]System.Xml.XmlDocument, bool)
0x2777e  stloc.s  7
0x27780  br       loc_2785B
0x27785  ldstr    aAppmodulecompo// "AppModuleComponent"
0x2778a  ldarg.0
0x2778b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::_context
0x27790  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x27795  stloc.s  9
0x27797  ldloc.s  9
0x27799  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x2779e  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x277a3  ldc.i4.0
0x277a4  ldloc.s  8
0x277a6  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x277ab  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x277b0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x277b5  pop
0x277b6  ldloc.s  9
0x277b8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x277bd  ldc.i4.2
0x277be  newarr   [mscorlib]System.String
0x277c3  dup
0x277c4  ldc.i4.0
0x277c5  ldstr    aComponenttype// "componenttype"
0x277ca  stelem.ref
0x277cb  dup
0x277cc  ldc.i4.1
0x277cd  ldstr    aObjectid// "objectid"
0x277d2  stelem.ref
0x277d3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x277d8  ldloc.1
0x277d9  ldloc.s  9
0x277db  ldarg.0
0x277dc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::_context
0x277e1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x277e6  stloc.s  0xA
0x277e8  ldarg.0
0x277e9  ldloc.s  8
0x277eb  ldloc.s  0xA
0x277ed  ldnull
0x277ee  ldnull
0x277ef  call     instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::GetAppModuleDefinition(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModule, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection appModuleComponents, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection appModuleRoleMaps, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> roleIdToRoleTemplateIdMap)
0x277f4  dup
0x277f5  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::AppConfig
0x277fa  stloc.s  0xB
0x277fc  ldloc.s  6
0x277fe  ldc.i4.0
0x277ff  ldstr    aRemoved// "Removed"
0x27804  ldstr    aAdded// "Added"
0x27809  ldstr    aAdded// "Added"
0x2780e  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::DiffAppModule(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition, bool, string, string, string)
0x27813  stloc.s  0xC
0x27815  ldc.i4.2
0x27816  newarr   [mscorlib]System.String
0x2781b  dup
0x2781c  ldc.i4.0
0x2781d  ldstr    aAdded// "Added"
0x27822  stelem.ref
0x27823  dup
0x27824  ldc.i4.1
0x27825  ldstr    aRemoved// "Removed"
0x2782a  stelem.ref
0x2782b  stloc.s  0xD
0x2782d  ldloc.s  0xC
0x2782f  ldloc.s  0xD
0x27831  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::GetAppModuleWithComponentAction(string[])
0x27836  stloc.s  0xC
0x27838  ldloc.s  0xC
0x2783a  ldloc.s  6
0x2783c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleRoleMapDefinition> [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_AppModuleRoleMaps()
0x27841  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::set_AppModuleRoleMaps(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleRoleMapDefinition>)
0x27846  ldloc.s  0xC
0x27848  ldloc.s  0xB
0x2784a  stfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::AppConfig
0x2784f  ldloc.3
0x27850  ldloc.s  0xC
0x27852  ldarg.1
0x27853  ldc.i4.1
0x27854  callvirt instance class [System.Xml]System.Xml.XmlNode [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleXmlSerializer::GetAppModuleXmlNode(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition, class [System.Xml]System.Xml.XmlDocument, bool)
0x27859  stloc.s  7
0x2785b  ldloc.s  6
0x2785d  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::AppConfig
0x27862  brfalse.s loc_2786D
0x27864  ldarg.0
0x27865  ldarg.1
0x27866  ldloc.s  7
0x27868  call     instance void Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::AppendNavigationSettingLabels(class [System.Xml]System.Xml.XmlDocument exportDocument, class [System.Xml]System.Xml.XmlNode appModuleXmlNode)
0x2786d  ldarg.0
0x2786e  ldloc.s  6
0x27870  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition::get_AppModuleId()
0x27875  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::GetLabelColumnNameNodePluralNameMap()
0x2787a  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppModulesUtility::GetNodePluralNameSingularNameMap()
0x2787f  ldarg.1
0x27880  ldloc.s  7
0x27882  ldstr    aAppmodule// "AppModule"
0x27887  call     instance void Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::AppendLabels(valuetype [mscorlib]System.Guid appModuleId, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> labelColumnNameNodePluralNameMap, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> nodePluralNameSingularNameMap, class [System.Xml]System.Xml.XmlDocument xmlDocument, class [System.Xml]System.Xml.XmlNode appModuleNode, string platformName)
0x2788c  ldloc.s  4
0x2788e  ldloc.s  7
0x27890  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x27895  pop
0x27896  ldloca.s 5
0x27898  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition>::MoveNext()
0x2789d  brtrue   loc_2771C
0x278a2  leave.s  loc_278B2
0x278a4  ldloca.s 5
0x278a6  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppModule.AppModuleDefinition>
0x278ac  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x278b1  endfinally
0x278b2  leave.s  loc_278F4
0x278b4  stloc.s  0xE
0x278b6  ldloc.s  0xE
0x278b8  ldarg.0
0x278b9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::_context
0x278be  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x278c3  ldc.i4.s 0x47
0x278c5  ldstr    aAppmoduleexpor_4// "AppModuleExportHandler.ExportManagedIte"...
0x278ca  ldc.i4.1
0x278cb  newarr   [mscorlib]System.Object
0x278d0  dup
0x278d1  ldc.i4.0
0x278d2  ldloc.s  0xE
0x278d4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x278d9  stelem.ref
0x278da  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x278df  ldarg.0
0x278e0  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::_tracer
0x278e5  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::AppModuleExportErrorMessage
0x278ea  ldloc.s  0xE
0x278ec  ldc.i4.3
0x278ed  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ExportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x278f2  rethrow
0x278f4  ldarg.0
0x278f5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppModuleExportHandler::_context
0x278fa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x278ff  ldc.i4.s 0x47
0x27901  ldstr    aAppmoduleexpor_5// "AppModuleExportHandler.ExportManagedIte"...
0x27906  ldc.i4.0
0x27907  newarr   [mscorlib]System.Object
0x2790c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x27911  ret
```
