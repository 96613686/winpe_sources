# Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::ImportManagedAppConfig

- ea: `0x29160`
- end: `0x29488`
- name: `Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::ImportManagedAppConfig`
- size: `808`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x28fd0`

## callees

- `0x29160`
- `0x295b0`
- `0x63df0`

## string_xrefs

- `0x29214`: `componentstate`
- `0x291b6`: `appconfigimportxml`
- `0x2935b`: `appconfigimportxml`
- `0x2940f`: `appconfigimportxml`
- `0x29232`: `appconfigidunique`
- `0x29255`: `appconfigid`
- `0x29317`: `appconfigid`
- `0x2931e`: `appconfigid`
- `0x293c1`: `appconfigid`
- `0x293cd`: `appconfigid`

## pseudocode

```c

```

## disassembly

```asm
0x29160  ldarg.0
0x29161  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_context
0x29166  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2916b  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(valuetype [mscorlib]System.Guid)
0x29170  stloc.0
0x29171  ldarg.0
0x29172  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x29177  ldarg.2
0x29178  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::RetrieveUnpublishedAppConfig(valuetype [mscorlib]System.Guid)
0x2917d  stloc.0
0x2917e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x29183  stloc.1
0x29184  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x29189  stloc.2
0x2918a  ldloc.0
0x2918b  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x29190  brtrue.s loc_29204
0x29192  ldarg.0
0x29193  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_context
0x29198  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2919d  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfig::.ctor(valuetype [mscorlib]System.Guid)
0x291a2  stloc.3
0x291a3  ldarg.0
0x291a4  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x291a9  ldloc.3
0x291aa  ldarg.0
0x291ab  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfig
0x291b0  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::PopulateAppConfigEntity(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfig, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition)
0x291b5  ldloc.3
0x291b6  ldstr    aAppconfigimpor// "appconfigimportxml"
0x291bb  ldarg.1
0x291bc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x291c1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x291c6  ldarg.0
0x291c7  ldarg.2
0x291c8  ldloc.3
0x291c9  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::CreateAppConfig(valuetype [mscorlib]System.Guid appModuleId, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfig appConfigEntity)
0x291ce  stloc.2
0x291cf  ldarg.0
0x291d0  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x291d5  ldarg.0
0x291d6  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfig
0x291db  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigInstanceDefinition> [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition::get_AppConfigInstances()
0x291e0  ldloc.2
0x291e1  ldc.i4.0
0x291e2  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::CreateAppConfigInstances(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigInstanceDefinition>, valuetype [mscorlib]System.Guid, bool)
0x291e7  ldarg.0
0x291e8  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x291ed  ldarg.0
0x291ee  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfig
0x291f3  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.NavigationSettingDefinition> [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition::get_NavigationSettings()
0x291f8  ldloc.2
0x291f9  ldc.i4.0
0x291fa  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::CreateNavigationSettings(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.NavigationSettingDefinition>, valuetype [mscorlib]System.Guid, bool)
0x291ff  br       loc_29469
0x29204  ldloc.0
0x29205  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x2920a  ldc.i4.0
0x2920b  ble.s    loc_29228
0x2920d  ldloc.0
0x2920e  ldc.i4.0
0x2920f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x29214  ldstr    aComponentstate_0// "componentstate"
0x29219  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2921e  unbox.any [mscorlib]System.Int32
0x29223  ldc.i4.1
0x29224  ceq
0x29226  br.s     loc_29229
0x29228  ldc.i4.0
0x29229  brfalse.s loc_2924E
0x2922b  ldloc.0
0x2922c  ldc.i4.0
0x2922d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x29232  ldstr    aAppconfigiduni// "appconfigidunique"
0x29237  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2923c  unbox.any [mscorlib]System.Guid
0x29241  stloc.1
0x29242  ldarg.0
0x29243  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x29248  ldloc.1
0x29249  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::RemoveUnPublishedRecords(valuetype [mscorlib]System.Guid)
0x2924e  ldloc.0
0x2924f  ldc.i4.0
0x29250  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x29255  ldstr    aAppconfigid// "appconfigid"
0x2925a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2925f  unbox.any [mscorlib]System.Guid
0x29264  stloc.2
0x29265  ldarg.0
0x29266  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x2926b  ldloc.2
0x2926c  ldc.i4   0xBF
0x29271  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::RetrieveEntityStates(valuetype [mscorlib]System.Guid, int32)
0x29276  stloc.s  4
0x29278  ldloc.s  4
0x2927a  ldarg.0
0x2927b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_context
0x29280  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x29285  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x2928a  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::IsExistingSolution(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState, valuetype [mscorlib]System.Guid)
0x2928f  brfalse.s loc_292A7
0x29291  ldarg.0
0x29292  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x29297  ldarg.1
0x29298  ldloc.s  4
0x2929a  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::HandleSolutionUpdate(class [System.Xml]System.Xml.XmlNode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState)
0x2929f  ldloc.2
0x292a0  stloc.s  9
0x292a2  leave    loc_29485
0x292a7  ldarg.0
0x292a8  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x292ad  ldloc.2
0x292ae  ldarg.0
0x292af  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfig
0x292b4  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition::get_AppModuleUniqueName()
0x292b9  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::CalculateCustomizationDiff(valuetype [mscorlib]System.Guid, string)
0x292be  stloc.s  5
0x292c0  ldloc.s  4
0x292c2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::GetLastManagedEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState)
0x292c7  stloc.s  6
0x292c9  ldarg.0
0x292ca  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x292cf  ldloc.s  6
0x292d1  ldarg.0
0x292d2  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfig
0x292d7  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition::get_AppModuleUniqueName()
0x292dc  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::GetAppConfigDefinition(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, string)
0x292e1  stloc.s  7
0x292e3  ldnull
0x292e4  stloc.s  8
0x292e6  ldloc.s  7
0x292e8  brfalse  loc_29390
0x292ed  ldarg.0
0x292ee  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x292f3  ldloc.s  7
0x292f5  ldarg.0
0x292f6  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfig
0x292fb  ldc.i4.0
0x292fc  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::DiffAppConfig(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition, bool)
0x29301  stloc.s  8
0x29303  ldarg.0
0x29304  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_context
0x29309  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2930e  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfig::.ctor(valuetype [mscorlib]System.Guid)
0x29313  stloc.s  0xA
0x29315  ldloc.s  0xA
0x29317  ldstr    aAppconfigid// "appconfigid"
0x2931c  ldloc.s  6
0x2931e  ldstr    aAppconfigid// "appconfigid"
0x29323  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x29328  unbox.any [mscorlib]System.Guid
0x2932d  box      [mscorlib]System.Guid
0x29332  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x29337  ldloc.s  0xA
0x29339  ldstr    aAppmoduleid// "appmoduleid"
0x2933e  ldloc.s  6
0x29340  ldstr    aAppmoduleid// "appmoduleid"
0x29345  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2934a  unbox.any [mscorlib]System.Guid
0x2934f  box      [mscorlib]System.Guid
0x29354  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x29359  ldloc.s  0xA
0x2935b  ldstr    aAppconfigimpor// "appconfigimportxml"
0x29360  ldarg.1
0x29361  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x29366  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2936b  ldarg.0
0x2936c  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x29371  ldloc.s  0xA
0x29373  ldloc.s  8
0x29375  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::PopulateAppConfigEntity(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfig, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition)
0x2937a  ldarg.0
0x2937b  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x29380  ldloc.s  0xA
0x29382  ldloc.s  8
0x29384  ldc.i4.1
0x29385  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::MergeAppConfig(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfig, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition, bool)
0x2938a  stloc.2
0x2938b  br       loc_2944C
0x29390  ldloc.s  5
0x29392  brfalse  loc_2944C
0x29397  ldarg.0
0x29398  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x2939d  ldloc.s  5
0x2939f  ldarg.0
0x293a0  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfig
0x293a5  ldc.i4.0
0x293a6  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::DiffAppConfig(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition, bool)
0x293ab  stloc.s  8
0x293ad  ldarg.0
0x293ae  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_context
0x293b3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x293b8  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfig::.ctor(valuetype [mscorlib]System.Guid)
0x293bd  stloc.s  0xB
0x293bf  ldloc.s  0xB
0x293c1  ldstr    aAppconfigid// "appconfigid"
0x293c6  ldloc.0
0x293c7  ldc.i4.0
0x293c8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x293cd  ldstr    aAppconfigid// "appconfigid"
0x293d2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x293d7  unbox.any [mscorlib]System.Guid
0x293dc  box      [mscorlib]System.Guid
0x293e1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x293e6  ldloc.s  0xB
0x293e8  ldstr    aAppmoduleid// "appmoduleid"
0x293ed  ldloc.0
0x293ee  ldc.i4.0
0x293ef  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x293f4  ldstr    aAppmoduleid// "appmoduleid"
0x293f9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x293fe  unbox.any [mscorlib]System.Guid
0x29403  box      [mscorlib]System.Guid
0x29408  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2940d  ldloc.s  0xB
0x2940f  ldstr    aAppconfigimpor// "appconfigimportxml"
0x29414  ldarg.1
0x29415  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x2941a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2941f  ldarg.0
0x29420  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x29425  ldloca.s 8
0x29427  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::RemoveChildrenWithUnModifiedSolutionAction(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition&)
0x2942c  ldarg.0
0x2942d  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x29432  ldloc.s  0xB
0x29434  ldloc.s  8
0x29436  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::PopulateAppConfigEntity(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfig, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition)
0x2943b  ldarg.0
0x2943c  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x29441  ldloc.s  0xB
0x29443  ldloc.s  8
0x29445  ldc.i4.1
0x29446  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::MergeAppConfig(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppConfig, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition, bool)
0x2944b  stloc.2
0x2944c  ldloc.s  5
0x2944e  brfalse.s loc_29469
0x29450  ldarg.0
0x29451  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfigUtility
0x29456  ldloc.2
0x29457  ldloc.s  5
0x29459  ldarg.0
0x2945a  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_appConfig
0x2945f  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition::get_AppModuleUniqueName()
0x29464  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AppConfigUtility::InstallCustomization(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.AppConfig.AppConfigDefinition, string)
0x29469  ldloc.2
0x2946a  stloc.s  9
0x2946c  leave.s  loc_29485
0x2946e  stloc.s  0xC
0x29470  ldarg.0
0x29471  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.AppConfigInstaller::_tracer
0x29476  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::AppConfigImportErrorMessage
0x2947b  ldloc.s  0xC
0x2947d  ldc.i4.3
0x2947e  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x29483  rethrow
0x29485  ldloc.s  9
0x29487  ret
```
