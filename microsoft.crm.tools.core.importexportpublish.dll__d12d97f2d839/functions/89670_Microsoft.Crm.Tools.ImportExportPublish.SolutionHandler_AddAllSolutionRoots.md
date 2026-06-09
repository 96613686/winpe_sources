# Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::AddAllSolutionRoots

- ea: `0x89670`
- end: `0x89beb`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::AddAllSolutionRoots`
- size: `1403`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x88c00`

## callees

- `0x2dbd0`
- `0x38bc0`
- `0x3aa70`
- `0x70440`
- `0x76a10`
- `0x76d00`
- `0x89670`
- `0x89bf0`
- `0x89c50`
- `0x89d80`
- `0x8a6e0`
- `0x8ac80`
- `0x8dad0`
- `0x97980`
- `0x979f0`

## string_xrefs

- `0x896ad`: `componenttype`
- `0x89771`: `componenttype`
- `0x89b04`: `componenttype`
- `0x896b5`: `rootcomponentbehavior`
- `0x8979f`: `rootcomponentbehavior`
- `0x89b34`: `rootcomponentbehavior`
- `0x89686`: `SolutionComponent`

## pseudocode

```c

```

## disassembly

```asm
0x89670  ldarg.1
0x89671  ldstr    aImportdocument// "importDocument"
0x89676  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8967b  ldarg.2
0x8967c  ldstr    aRootnode// "rootNode"
0x89681  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x89686  ldstr    aSolutioncompon// "SolutionComponent"
0x8968b  ldarg.0
0x8968c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x89691  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x89696  stloc.0
0x89697  ldloc.0
0x89698  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x8969d  ldc.i4.3
0x8969e  newarr   [mscorlib]System.String
0x896a3  dup
0x896a4  ldc.i4.0
0x896a5  ldstr    aObjectid// "objectid"
0x896aa  stelem.ref
0x896ab  dup
0x896ac  ldc.i4.1
0x896ad  ldstr    aComponenttype// "componenttype"
0x896b2  stelem.ref
0x896b3  dup
0x896b4  ldc.i4.2
0x896b5  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x896ba  stelem.ref
0x896bb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x896c0  ldloc.0
0x896c1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x896c6  ldstr    aSolutionid// "solutionid"
0x896cb  ldc.i4.0
0x896cc  ldarg.3
0x896cd  box      [mscorlib]System.Guid
0x896d2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x896d7  pop
0x896d8  ldloc.0
0x896d9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x896de  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata)
0x896e3  ldloc.0
0x896e4  ldarg.0
0x896e5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x896ea  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x896ef  stloc.1
0x896f0  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyFilter::.ctor()
0x896f5  ldloc.1
0x896f6  ldarg.0
0x896f7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x896fc  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyFilter::FilterHiddenComponents(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x89701  stloc.1
0x89702  ldloc.1
0x89703  ldarg.0
0x89704  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x89709  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::AddInteractionCentricDashboardRoots(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection collection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8970e  stloc.2
0x8970f  ldc.i4.0
0x89710  stloc.3
0x89711  ldc.i4.0
0x89712  stloc.s  4
0x89714  ldloc.1
0x89715  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x8971a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo>::.ctor(int32)
0x8971f  stloc.s  5
0x89721  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SolutionCache::Instance()
0x89726  ldarg.3
0x89727  ldarg.0
0x89728  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x8972d  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution>::LookupEntry(void, var<u1>)
0x89732  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISolution::get_UniqueName()
0x89737  stloc.s  6
0x89739  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x8973e  ldarg.0
0x8973f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x89744  call     class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ConverterUtilities::GetCustomControlsForExport(class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x89749  stloc.s  7
0x8974b  ldloc.1
0x8974c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x89751  stloc.s  8
0x89753  br       loc_89ABB
0x89758  ldloc.s  8
0x8975a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8975f  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x89764  stloc.s  9
0x89766  newobj   instance void <>c__DisplayClass15_0::.ctor()
0x8976b  stloc.s  0xA
0x8976d  ldloc.s  0xA
0x8976f  ldloc.s  9
0x89771  ldstr    aComponenttype// "componenttype"
0x89776  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x8977b  unbox.any [mscorlib]System.Int32
0x89780  stfld    int32 <>c__DisplayClass15_0::componentType
0x89785  ldloc.s  0xA
0x89787  ldloc.s  9
0x89789  ldstr    aObjectid// "objectid"
0x8978e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x89793  unbox.any [mscorlib]System.Guid
0x89798  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass15_0::objectId
0x8979d  ldloc.s  9
0x8979f  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x897a4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x897a9  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0x897ae  stloc.s  0xB
0x897b0  ldarg.0
0x897b1  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::get_ExportToTargetVersionContext()
0x897b6  ldloc.s  0xA
0x897b8  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass15_0::objectId
0x897bd  ldloc.s  0xA
0x897bf  ldfld    int32 <>c__DisplayClass15_0::componentType
0x897c4  newobj   instance void class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32>::.ctor(var<u1>, !!T0)
0x897c9  callvirt instance valuetype Microsoft.Crm.Tools.ImportExportPublish.ComponentAction Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext::ActionToBeTakenOnComponent(class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, int32> dependentComponent)
0x897ce  ldc.i4.1
0x897cf  beq      loc_89ABB
0x897d4  ldloc.s  0xA
0x897d6  ldfld    int32 <>c__DisplayClass15_0::componentType
0x897db  ldc.i4.s 0x42
0x897dd  bne.un.s loc_897FE
0x897df  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x897e4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x897e9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_CustomControlSolutionExport()
0x897ee  ldarg.0
0x897ef  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x897f4  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x897f9  brfalse  loc_89ABB
0x897fe  ldloc.s  0xA
0x89800  ldfld    int32 <>c__DisplayClass15_0::componentType
0x89805  ldc.i4.s 0x50
0x89807  bne.un.s loc_8981B
0x89809  ldarg.0
0x8980a  ldloc.s  0xA
0x8980c  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass15_0::objectId
0x89811  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::IsAppModuleExportable(valuetype [mscorlib]System.Guid objectId)
0x89816  brfalse  loc_89ABB
0x8981b  ldloc.s  0xA
0x8981d  ldfld    int32 <>c__DisplayClass15_0::componentType
0x89822  ldc.i4.s 0x3E
0x89824  bne.un.s loc_89869
0x89826  ldloc.s  0xA
0x89828  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass15_0::objectId
0x8982d  ldarg.0
0x8982e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x89833  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SiteMapSolutionUtility::IsDefaultSiteMap(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x89838  brtrue.s loc_89869
0x8983a  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x8983f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x89844  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AppModuleForOrganization()
0x89849  ldarg.0
0x8984a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x8984f  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x89854  brfalse  loc_89ABB
0x89859  ldarg.0
0x8985a  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::get_ExportToTargetVersionContext()
0x8985f  call     bool Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::IsExportingToLowerVersion(class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext)
0x89864  brtrue   loc_89ABB
0x89869  ldloc.s  0xA
0x8986b  ldfld    int32 <>c__DisplayClass15_0::componentType
0x89870  ldloc.s  0xA
0x89872  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass15_0::objectId
0x89877  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8987c  ldloc.s  4
0x8987e  dup
0x8987f  ldc.i4.1
0x89880  add
0x89881  stloc.s  4
0x89883  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::.ctor(int32, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32)
0x89888  stloc.s  0xC
0x8988a  ldloc.s  0xC
0x8988c  ldloc.s  0xB
0x8988e  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::set_RootComponentBehavior(valuetype [mscorlib]System.Nullable`1<int32>)
0x89893  ldloc.s  0xA
0x89895  ldfld    int32 <>c__DisplayClass15_0::componentType
0x8989a  ldloca.s 0xD
0x8989c  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::TryRetrieveHelper(int32, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper&)
0x898a1  brfalse  loc_89ABB
0x898a6  ldloc.s  0xD
0x898a8  ldloc.s  0xC
0x898aa  ldarg.0
0x898ab  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x898b0  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::FillComponentInfoForExport(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x898b5  ldloc.s  0xC
0x898b7  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentType()
0x898bc  ldc.i4.s 0x32
0x898be  bne.un.s loc_898C8
0x898c0  ldloc.3
0x898c1  brtrue   loc_89ABB
0x898c6  ldc.i4.1
0x898c7  stloc.3
0x898c8  ldloc.s  0xC
0x898ca  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentType()
0x898cf  ldc.i4.s 0x3D
0x898d1  bne.un.s loc_898DF
0x898d3  ldloc.s  0xC
0x898d5  callvirt instance bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_Resolved()
0x898da  brfalse  loc_89ABB
0x898df  ldloc.s  0xC
0x898e1  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentType()
0x898e6  ldc.i4.1
0x898e7  bne.un.s loc_898FD
0x898e9  ldarg.0
0x898ea  ldloc.s  6
0x898ec  ldloc.s  0xA
0x898ee  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass15_0::objectId
0x898f3  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::FilterEntityForExport(string solutionName, valuetype [mscorlib]System.Guid objectId)
0x898f8  brtrue   loc_89ABB
0x898fd  ldloc.s  0xC
0x898ff  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentType()
0x89904  ldc.i4.s 9
0x89906  bne.un.s loc_89925
0x89908  ldloc.s  0xA
0x8990a  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass15_0::objectId
0x8990f  ldarg.0
0x89910  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_dmc
0x89915  ldarg.0
0x89916  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::get_ExportToTargetVersionContext()
0x8991b  call     bool Microsoft.Crm.Tools.ImportExportPublish.OptionSetsHandler::ShouldOptionSetBeExported(valuetype [mscorlib]System.Guid optionSetId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache metadataCache, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext ExportToTargetVersionContext)
0x89920  brfalse  loc_89ABB
0x89925  ldloc.s  0xC
0x89927  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentType()
0x8992c  ldc.i4   0x98
0x89931  bne.un.s loc_89950
0x89933  ldloc.s  0xA
0x89935  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass15_0::objectId
0x8993a  ldarg.0
0x8993b  call     instance class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::get_ExportToTargetVersionContext()
0x89940  ldarg.0
0x89941  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x89946  call     bool Microsoft.Crm.Tools.ImportExportPublish.SLAHandler::ShouldSlaBeExported(valuetype [mscorlib]System.Guid slaId, class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8994b  brfalse  loc_89ABB
0x89950  ldloc.s  0xC
0x89952  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentType()
0x89957  ldc.i4.s 0x3C
0x89959  bne.un.s loc_89972
0x8995b  ldloc.s  0xA
0x8995d  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass15_0::objectId
0x89962  ldarg.0
0x89963  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x89968  call     bool Microsoft.Crm.Tools.ImportExportPublish.WorkflowHandler::ShouldProcessActionFormXmlBeExported(valuetype [mscorlib]System.Guid formId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8996d  brfalse  loc_89ABB
0x89972  ldloc.s  0xC
0x89974  callvirt instance int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ComponentType()
0x89979  ldc.i4.s 0x42
0x8997b  bne.un.s loc_899C3
0x8997d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x89982  stloc.s  0xE
0x89984  ldloc.s  7
0x89986  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::get_Keys()
0x8998b  call     T0x2B00006A
0x89990  brfalse.s loc_899B2
0x89992  ldloc.s  7
0x89994  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, string>::get_Keys()
0x89999  ldloc.s  0xA
0x8999b  ldftn    instance bool <>c__DisplayClass15_0::<AddAllSolutionRoots>b__0(valuetype [mscorlib]System.Guid ck)
0x899a1  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, bool>::.ctor(object, native int)
0x899a6  call     T0x2B00001F
0x899ab  call     T0x2B00006B
0x899b0  stloc.s  0xE
0x899b2  ldloc.s  0xE
0x899b4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x899b9  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x899be  brtrue   loc_89ABB
0x899c3  ldloc.s  0xA
0x899c5  ldfld    int32 <>c__DisplayClass15_0::componentType
0x899ca  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentTypeMap::IsRoot(int32)
0x899cf  brtrue.s loc_899F1
0x899d1  ldloc.s  0xC
0x899d3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo::get_ObjectId()
0x899d8  ldloc.s  0xA
0x899da  ldfld    int32 <>c__DisplayClass15_0::componentType
0x899df  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentMoniker::.ctor(valuetype [mscorlib]System.Guid, int32)
0x899e4  ldarg.0
0x899e5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x899ea  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentHelper::IsComponentInstanceRoot(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.SolutionComponentMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x899ef  brfalse.s loc_899FA
0x899f1  ldloc.s  5
0x899f3  ldloc.s  0xC
0x899f5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ComponentInfo>::Add(var<u1>)
0x899fa  ldloc.s  0xA
0x899fc  ldfld    int32 <>c__DisplayClass15_0::componentType
0x89a01  ldc.i4.1
0x89a02  bne.un   loc_89ABB
0x89a07  ldarg.0
0x89a08  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_dmc
0x89a0d  ldloc.s  0xA
0x89a0f  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass15_0::objectId
0x89a14  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x89a19  stloc.s  0xF
0x89a1b  ldloc.s  0xF
0x89a1d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsBPFEntity()
0x89a22  call     bool [mscorlib]System.Convert::ToBoolean(bool)
0x89a27  brfalse  loc_89ABB
0x89a2c  ldloc.s  0xF
0x89a2e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x89a33  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_LogicalName()
0x89a38  ldarg.0
0x89a39  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.SolutionHandler::_context
0x89a3e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::GetAllExportableWorkflows(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x89a43  call     class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity Microsoft.Crm.Tools.ImportExportPublish.RootExportHandler::GetBpfDefinitionToBeAdded(string entityname, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection workflows)
0x89a48  stloc.s  0x10
0x89a4a  ldloc.s  0x10
0x89a4c  brfalse.s loc_89ABB
0x89a4e  ldloc.s  0xA
  ... truncated ...
```
