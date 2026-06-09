# Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::OnSaveHandler

- ea: `0xd880`
- end: `0xd9c0`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::OnSaveHandler`
- size: `320`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xd6d0`
- `0xd880`
- `0xd9c0`

## pseudocode

```c

```

## disassembly

```asm
0xd880  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd885  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xd88a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xd88f  stloc.0
0xd890  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xd895  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xd89a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AnyChanelToAnyEntityRecordCreation()
0xd89f  ldloc.0
0xd8a0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd8a5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0xd8aa  ldloc.0
0xd8ab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd8b0  ldloc.0
0xd8b1  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0xd8b6  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0xd8bb  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0xd8c0  stloc.1
0xd8c1  ldloc.1
0xd8c2  brtrue.s loc_D8C5
0xd8c4  ret
0xd8c5  ldarg.0
0xd8c6  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xd8cb  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0xd8d0  ldc.i4.1
0xd8d1  bne.un   loc_D988
0xd8d6  ldarg.0
0xd8d7  ldloc.1
0xd8d8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::GetConvertRule(bool isFeatureEnabled)
0xd8dd  stloc.2
0xd8de  ldloc.2
0xd8df  brfalse  loc_D9BF
0xd8e4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd8e9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd8ee  ldloc.2
0xd8ef  ldstr    aSourcechannelt// "sourcechanneltypecode"
0xd8f4  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd8f9  unbox.any [mscorlib]System.Int32
0xd8fe  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xd903  stloc.3
0xd904  ldarg.0
0xd905  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd90a  ldloc.3
0xd90b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xd910  ldc.i4.1
0xd911  newobj   instance void [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, string, valuetype [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAction)
0xd916  stloc.s  4
0xd918  ldarg.0
0xd919  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd91e  ldstr    aWorkflowid// "workflowid"
0xd923  ldloc.s  4
0xd925  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowErrorVisitorContext::.ctor()
0xd92a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::CreateWorkflow(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext)
0xd92f  box      [mscorlib]System.Guid
0xd934  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xd939  newobj   instance void [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::.ctor()
0xd93e  ldarg.0
0xd93f  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd944  ldstr    aWorkflowid// "workflowid"
0xd949  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd94e  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xd953  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xd958  ldloc.2
0xd959  ldstr    aChannelpropert// "channelpropertygroupid"
0xd95e  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttributeAndNotNull(string)
0xd963  brtrue.s loc_D968
0xd965  ldnull
0xd966  br.s     loc_D97D
0xd968  ldloc.2
0xd969  ldstr    aChannelpropert// "channelpropertygroupid"
0xd96e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd973  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xd978  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xd97d  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowErrorVisitorContext::.ctor()
0xd982  callvirt instance void [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddInputVariablesToConvertRuleItemWorkflow(string, string, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext)
0xd987  ret
0xd988  ldarg.0
0xd989  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xd98e  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0xd993  ldc.i4.2
0xd994  bne.un.s loc_D9BF
0xd996  ldarg.0
0xd997  ldarg.0
0xd998  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd99d  call     instance bool Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::WorkflowUpdateRequired(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0xd9a2  brfalse.s loc_D9BF
0xd9a4  ldarg.0
0xd9a5  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd9aa  ldsfld   string [mscorlib]System.String::Empty
0xd9af  ldc.i4.2
0xd9b0  newobj   instance void [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, string, valuetype [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAction)
0xd9b5  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowErrorVisitorContext::.ctor()
0xd9ba  callvirt instance void [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.ConvertRuleItemWorkflowAuthoringHelper::UpdateWorkflow(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext)
0xd9bf  ret
```
