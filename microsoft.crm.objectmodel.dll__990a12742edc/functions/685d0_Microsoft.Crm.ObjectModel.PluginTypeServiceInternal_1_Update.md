# Microsoft.Crm.ObjectModel.PluginTypeServiceInternal`1::Update

- ea: `0x685d0`
- end: `0x68859`
- name: `Microsoft.Crm.ObjectModel.PluginTypeServiceInternal`1::Update`
- size: `649`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x68370`
- `0x685d0`
- `0xe5600`
- `0x170200`
- `0x1bfb60`

## string_xrefs

- `0x685f7`: `plugintypeid`
- `0x68633`: `pluginassemblyid`
- `0x68651`: `pluginassemblyid`
- `0x686a7`: `pluginassemblyid`
- `0x68734`: `pluginassemblyid`
- `0x68741`: `pluginassemblyid`
- `0x68747`: `pluginassemblyid`
- `0x68622`: `Cannot update system plugin types`

## pseudocode

```c

```

## disassembly

```asm
0x685d0  ldarg.1
0x685d1  ldstr    aEntity_0// "entity"
0x685d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x685db  ldarg.2
0x685dc  ldstr    aContext// "context"
0x685e1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x685e6  ldarg.1
0x685e7  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginType
0x685ec  stloc.0
0x685ed  ldarg.2
0x685ee  callvirt instance valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.OperationContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_OperationContext()
0x685f3  brfalse.s loc_68632
0x685f5  ldarg.1
0x685f6  ldarg.1
0x685f7  ldstr    aPlugintypeid// "plugintypeid"
0x685fc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x68601  unbox.any [mscorlib]System.Guid
0x68606  ldarg.2
0x68607  ldarg.0
0x68608  call     int32 Microsoft.Crm.ObjectModel.PluginUtility::RetrieveCustomizationLevel(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service)
0x6860d  brtrue.s loc_68632
0x6860f  ldarg.2
0x68610  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x68615  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x6861a  ldarg.2
0x6861b  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.SolutionHelper::IsInternalSystemConvertedSolution(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x68620  brtrue.s loc_68632
0x68622  ldstr    aCannotUpdateSy// "Cannot update system plugin types"
0x68627  ldc.i4   0x80040358
0x6862c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x68631  throw
0x68632  ldloc.0
0x68633  ldstr    aPluginassembly// "pluginassemblyid"
0x68638  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6863d  brtrue.s loc_6864F
0x6863f  ldloc.0
0x68640  ldstr    aTypename// "typename"
0x68645  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6864a  ldnull
0x6864b  cgt.un
0x6864d  br.s     loc_68650
0x6864f  ldc.i4.1
0x68650  ldloc.0
0x68651  ldstr    aPluginassembly// "pluginassemblyid"
0x68656  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6865b  brfalse.s loc_68694
0x6865d  ldloc.0
0x6865e  ldstr    aTypename// "typename"
0x68663  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x68668  brfalse.s loc_68694
0x6866a  ldloc.0
0x6866b  ldstr    aIsworkflowacti// "isworkflowactivity"
0x68670  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x68675  brfalse.s loc_68694
0x68677  ldloc.0
0x68678  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0x6867d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x68682  brfalse.s loc_68694
0x68684  ldloc.0
0x68685  ldstr    aName// "name"
0x6868a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6868f  brtrue   loc_68809
0x68694  ldarg.1
0x68695  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x6869a  ldarg.2
0x6869b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x686a0  stloc.1
0x686a1  ldloc.1
0x686a2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x686a7  ldstr    aPluginassembly// "pluginassemblyid"
0x686ac  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x686b1  ldloc.1
0x686b2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x686b7  ldstr    aTypename// "typename"
0x686bc  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x686c1  ldloc.1
0x686c2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x686c7  ldstr    aIsworkflowacti// "isworkflowactivity"
0x686cc  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x686d1  ldloc.1
0x686d2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x686d7  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0x686dc  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x686e1  ldloc.1
0x686e2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x686e7  ldstr    aName// "name"
0x686ec  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x686f1  ldloc.1
0x686f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Entity()
0x686f7  ldstr    aCustomworkflow// "customworkflowactivityinfo"
0x686fc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x68701  brfalse.s loc_68713
0x68703  ldloc.1
0x68704  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x68709  ldstr    aCustomworkflow// "customworkflowactivityinfo"
0x6870e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x68713  ldarg.0
0x68714  ldarg.1
0x68715  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x6871a  unbox.any [mscorlib]System.Guid
0x6871f  ldarg.1
0x68720  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x68725  ldarg.2
0x68726  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6872b  ldloc.1
0x6872c  ldarg.2
0x6872d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x68732  stloc.2
0x68733  ldloc.0
0x68734  ldstr    aPluginassembly// "pluginassemblyid"
0x68739  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6873e  brtrue.s loc_68756
0x68740  ldloc.0
0x68741  ldstr    aPluginassembly// "pluginassemblyid"
0x68746  ldloc.2
0x68747  ldstr    aPluginassembly// "pluginassemblyid"
0x6874c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x68751  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x68756  ldloc.0
0x68757  ldstr    aTypename// "typename"
0x6875c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x68761  brtrue.s loc_68779
0x68763  ldloc.0
0x68764  ldstr    aTypename// "typename"
0x68769  ldloc.2
0x6876a  ldstr    aTypename// "typename"
0x6876f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x68774  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x68779  ldloc.0
0x6877a  ldstr    aIsworkflowacti// "isworkflowactivity"
0x6877f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x68784  brtrue.s loc_687A9
0x68786  ldloc.2
0x68787  ldstr    aIsworkflowacti// "isworkflowactivity"
0x6878c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x68791  brtrue.s loc_687A9
0x68793  ldloc.0
0x68794  ldstr    aIsworkflowacti// "isworkflowactivity"
0x68799  ldloc.2
0x6879a  ldstr    aIsworkflowacti// "isworkflowactivity"
0x6879f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x687a4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x687a9  ldloc.0
0x687aa  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0x687af  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x687b4  brtrue.s loc_687D9
0x687b6  ldloc.2
0x687b7  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0x687bc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x687c1  brtrue.s loc_687D9
0x687c3  ldloc.0
0x687c4  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0x687c9  ldloc.2
0x687ca  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0x687cf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x687d4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x687d9  ldloc.0
0x687da  ldstr    aName// "name"
0x687df  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x687e4  brtrue.s loc_68809
0x687e6  ldloc.2
0x687e7  ldstr    aName// "name"
0x687ec  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x687f1  brtrue.s loc_68809
0x687f3  ldloc.0
0x687f4  ldstr    aName// "name"
0x687f9  ldloc.2
0x687fa  ldstr    aName// "name"
0x687ff  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x68804  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x68809  brfalse.s loc_68850
0x6880b  ldarg.2
0x6880c  callvirt instance valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.OperationContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_OperationContext()
0x68811  brfalse.s loc_68850
0x68813  ldarg.0
0x68814  ldarg.1
0x68815  ldarg.2
0x68816  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class Microsoft.Crm.ObjectModel.PluginTypeServiceInternal`1<var<u1>>::GetParentAssembly(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6881b  stloc.3
0x6881c  ldnull
0x6881d  stloc.s  4
0x6881f  ldnull
0x68820  stloc.s  5
0x68822  ldarg.0
0x68823  ldloc.0
0x68824  ldloc.3
0x68825  ldloca.s 4
0x68827  ldloca.s 5
0x68829  ldarg.2
0x6882a  call     instance void class Microsoft.Crm.ObjectModel.PluginTypeServiceInternal`1<var<u1>>::SetIsWorkFlowActivityAttribute(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PluginType, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo&, class [Microsoft.Crm]Microsoft.Crm.CrmPluginTypeMetadata&, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6882f  ldarg.2
0x68830  ldloc.3
0x68831  ldloc.0
0x68832  ldloca.s 6
0x68834  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x6883a  ldloc.s  6
0x6883c  ldarg.0
0x6883d  ldloc.3
0x6883e  ldarg.2
0x6883f  call     instance class [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata class Microsoft.Crm.ObjectModel.PluginTypeServiceInternal`1<var<u1>>::GetParentAssemblyMetadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x68844  ldloc.s  4
0x68846  newobj   instance void Microsoft.Crm.ObjectModel.PluginTypeValidator::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity pluginAssembly, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity pluginType, valuetype [mscorlib]System.Nullable`1<bool> isWorkflowActivity, class [Microsoft.Crm]Microsoft.Crm.CrmPluginAssemblyMetadata parentAssemblyMetadata, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo customActivityInfo)
0x6884b  callvirt instance void Microsoft.Crm.ObjectModel.PluginValidatorBase::Validate()
0x68850  ldarg.0
0x68851  ldloc.0
0x68852  ldarg.2
0x68853  call     instance void Microsoft.Crm.ObjectModel.SdkEntityServiceBase::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x68858  ret
```
