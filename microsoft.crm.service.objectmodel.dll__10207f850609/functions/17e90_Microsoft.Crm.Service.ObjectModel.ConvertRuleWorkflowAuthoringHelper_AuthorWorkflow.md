# Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AuthorWorkflow

- ea: `0x17e90`
- end: `0x1881f`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AuthorWorkflow`
- size: `2447`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x9310`

## callees

- `0x4f80`
- `0x17e90`
- `0x18880`
- `0x189f0`
- `0x18b00`
- `0x18b20`
- `0x18b40`
- `0x18cf0`
- `0x18d40`
- `0x18dc0`
- `0x191a0`
- `0x19490`
- `0x197f0`
- `0x19b80`

## string_xrefs

- `0x17ebb`: `responsetemplateid`
- `0x1802e`: `responsetemplateid`
- `0x18040`: `responsetemplateid`
- `0x18053`: `responsetemplateid`
- `0x180af`: `propertiesxml`
- `0x180eb`: `propertiesxml`
- `0x180b7`: `conditionxml`
- `0x180f3`: `conditionxml`
- `0x18469`: `conditionxml`
- `0x18477`: `conditionxml`
- `0x18496`: `conditionxml`
- `0x184bd`: `conditionxml`
- `0x185b2`: `conditionxml`
- `0x185c3`: `conditionxml`
- `0x1860f`: `conditionxml`
- `0x18632`: `conditionxml`

## pseudocode

```c

```

## disassembly

```asm
0x17e90  ldstr    aConvertrule_0// "convertrule"
0x17e95  stloc.0
0x17e96  ldstr    aConvertruleite_1// "convertruleitem"
0x17e9b  stloc.1
0x17e9c  ldc.i4.0
0x17e9d  stloc.2
0x17e9e  ldnull
0x17e9f  stloc.3
0x17ea0  ldarg.0
0x17ea1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x17ea6  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::responseTemplateId
0x17eab  ldc.i4.5
0x17eac  newarr   [mscorlib]System.String
0x17eb1  dup
0x17eb2  ldc.i4.0
0x17eb3  ldstr    aSendautomaticr// "sendautomaticresponse"
0x17eb8  stelem.ref
0x17eb9  dup
0x17eba  ldc.i4.1
0x17ebb  ldstr    aResponsetempla// "responsetemplateid"
0x17ec0  stelem.ref
0x17ec1  dup
0x17ec2  ldc.i4.2
0x17ec3  ldstr    aName// "name"
0x17ec8  stelem.ref
0x17ec9  dup
0x17eca  ldc.i4.3
0x17ecb  ldstr    aSourcetypecode// "sourcetypecode"
0x17ed0  stelem.ref
0x17ed1  dup
0x17ed2  ldc.i4.4
0x17ed3  ldstr    aOwnerid// "ownerid"
0x17ed8  stelem.ref
0x17ed9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x17ede  stloc.s  4
0x17ee0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17ee5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x17eea  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x17eef  stloc.s  5
0x17ef1  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x17ef6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x17efb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AnyChanelToAnyEntityRecordCreation()
0x17f00  ldloc.s  5
0x17f02  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x17f07  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x17f0c  ldloc.s  5
0x17f0e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x17f13  ldloc.s  5
0x17f15  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x17f1a  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x17f1f  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x17f24  stloc.s  6
0x17f26  ldloc.s  6
0x17f28  brfalse.s loc_17F47
0x17f2a  ldloc.s  4
0x17f2c  ldc.i4.2
0x17f2d  newarr   [mscorlib]System.String
0x17f32  dup
0x17f33  ldc.i4.0
0x17f34  ldstr    aSourcechannelt// "sourcechanneltypecode"
0x17f39  stelem.ref
0x17f3a  dup
0x17f3b  ldc.i4.1
0x17f3c  ldstr    aChannelpropert// "channelpropertygroupid"
0x17f41  stelem.ref
0x17f42  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x17f47  ldarg.0
0x17f48  ldarg.0
0x17f49  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x17f4e  ldloc.0
0x17f4f  ldarg.1
0x17f50  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x17f55  ldloc.s  4
0x17f57  ldc.i4.0
0x17f58  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet, bool)
0x17f5d  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::convertRuleEntity
0x17f62  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x17f67  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x17f6c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AnyChanelToAnyEntityRecordCreation()
0x17f71  ldloc.s  5
0x17f73  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x17f78  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x17f7d  ldloc.s  5
0x17f7f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x17f84  ldloc.s  5
0x17f86  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x17f8b  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x17f90  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x17f95  brfalse.s loc_17FB9
0x17f97  ldarg.0
0x17f98  ldarg.0
0x17f99  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::convertRuleEntity
0x17f9e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x17fa3  ldstr    aSourcechannelt// "sourcechanneltypecode"
0x17fa8  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x17fad  callvirt instance string [mscorlib]System.Object::ToString()
0x17fb2  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_PrimaryEntityName(string)
0x17fb7  br.s     loc_18006
0x17fb9  ldarg.0
0x17fba  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::convertRuleEntity
0x17fbf  ldstr    aSourcetypecode// "sourcetypecode"
0x17fc4  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x17fc9  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x17fce  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x17fd3  stloc.s  0x14
0x17fd5  ldloc.s  0x14
0x17fd7  ldc.i4.1
0x17fd8  beq.s    loc_17FE1
0x17fda  ldloc.s  0x14
0x17fdc  ldc.i4.2
0x17fdd  beq.s    loc_17FEE
0x17fdf  br.s     loc_17FFB
0x17fe1  ldarg.0
0x17fe2  ldstr    aSocialactivity// "socialactivity"
0x17fe7  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_PrimaryEntityName(string)
0x17fec  br.s     loc_18006
0x17fee  ldarg.0
0x17fef  ldstr    aEmail// "email"
0x17ff4  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_PrimaryEntityName(string)
0x17ff9  br.s     loc_18006
0x17ffb  ldc.i4.0
0x17ffc  ldstr    aInvalidSourceT// "Invalid source type code for the the cu"...
0x18001  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x18006  ldarg.0
0x18007  ldarg.0
0x18008  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::convertRuleEntity
0x1800d  ldstr    aSendautomaticr// "sendautomaticresponse"
0x18012  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x18017  unbox.any [mscorlib]System.Boolean
0x1801c  call     instance bool Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::isAutoResponseEnabled(bool autoResponse)
0x18021  brfalse.s loc_1806C
0x18023  ldarg.0
0x18024  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::convertRuleEntity
0x18029  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1802e  ldstr    aResponsetempla// "responsetemplateid"
0x18033  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x18038  brfalse.s loc_1806C
0x1803a  ldarg.0
0x1803b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::convertRuleEntity
0x18040  ldstr    aResponsetempla// "responsetemplateid"
0x18045  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1804a  brfalse.s loc_1806C
0x1804c  ldarg.0
0x1804d  ldarg.0
0x1804e  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::convertRuleEntity
0x18053  ldstr    aResponsetempla// "responsetemplateid"
0x18058  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1805d  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x18062  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x18067  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::responseTemplateId
0x1806c  ldloc.1
0x1806d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x18072  stloc.s  7
0x18074  ldloc.s  7
0x18076  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x1807b  ldstr    aConvertruleid_0// "convertruleid"
0x18080  ldc.i4.0
0x18081  ldarg.1
0x18082  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x18087  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0x1808c  ldloc.s  7
0x1808e  ldstr    aSequencenumber// "sequencenumber"
0x18093  ldc.i4.0
0x18094  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::AddOrder(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.OrderType)
0x18099  ldloc.s  6
0x1809b  brfalse.s loc_180D9
0x1809d  ldloc.s  7
0x1809f  ldc.i4.5
0x180a0  newarr   [mscorlib]System.String
0x180a5  dup
0x180a6  ldc.i4.0
0x180a7  ldstr    aSequencenumber// "sequencenumber"
0x180ac  stelem.ref
0x180ad  dup
0x180ae  ldc.i4.1
0x180af  ldstr    aPropertiesxml// "propertiesxml"
0x180b4  stelem.ref
0x180b5  dup
0x180b6  ldc.i4.2
0x180b7  ldstr    aConditionxml// "conditionxml"
0x180bc  stelem.ref
0x180bd  dup
0x180be  ldc.i4.3
0x180bf  ldstr    aWorkflowid// "workflowid"
0x180c4  stelem.ref
0x180c5  dup
0x180c6  ldc.i4.4
0x180c7  ldstr    aName// "name"
0x180cc  stelem.ref
0x180cd  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x180d2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x180d7  br.s     loc_18103
0x180d9  ldloc.s  7
0x180db  ldc.i4.3
0x180dc  newarr   [mscorlib]System.String
0x180e1  dup
0x180e2  ldc.i4.0
0x180e3  ldstr    aSequencenumber// "sequencenumber"
0x180e8  stelem.ref
0x180e9  dup
0x180ea  ldc.i4.1
0x180eb  ldstr    aPropertiesxml// "propertiesxml"
0x180f0  stelem.ref
0x180f1  dup
0x180f2  ldc.i4.2
0x180f3  ldstr    aConditionxml// "conditionxml"
0x180f8  stelem.ref
0x180f9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x180fe  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x18103  ldarg.0
0x18104  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_SdkCommand()
0x18109  ldloc.s  7
0x1810b  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.ISdkCommand::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression)
0x18110  stloc.s  8
0x18112  ldarg.0
0x18113  ldarg.0
0x18114  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::convertRuleEntity
0x18119  ldstr    aName// "name"
0x1811e  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x18123  callvirt instance string [mscorlib]System.Object::ToString()
0x18128  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_WorkflowName(string)
0x1812d  ldarg.0
0x1812e  ldc.i4.0
0x1812f  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_IsSyncWorkflow(bool)
0x18134  ldarg.0
0x18135  ldc.i4.0
0x18136  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::set_WorkflowCategory(int32)
0x1813b  ldarg.0
0x1813c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_WorkflowAdapter()
0x18141  ldarg.0
0x18142  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::convertRuleEntity
0x18147  ldstr    aOwnerid// "ownerid"
0x1814c  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x18151  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x18156  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::set_OverriddenOwnerId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x1815b  ldarg.0
0x1815c  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::CreateWorkflow()
0x18161  stloc.s  9
0x18163  ldloc.s  6
0x18165  brfalse.s loc_181C0
0x18167  ldarg.0
0x18168  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::convertRuleEntity
0x1816d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x18172  ldstr    aChannelpropert// "channelpropertygroupid"
0x18177  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0x1817c  brfalse.s loc_181C0
0x1817e  ldarg.0
0x1817f  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::convertRuleEntity
0x18184  ldstr    aChannelpropert// "channelpropertygroupid"
0x18189  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1818e  brfalse.s loc_181C0
0x18190  ldloc.s  9
0x18192  ldarg.0
0x18193  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::convertRuleEntity
0x18198  ldstr    aChannelpropert// "channelpropertygroupid"
0x1819d  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x181a2  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x181a7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x181ac  stloc.s  0x15
0x181ae  ldloca.s 0x15
0x181b0  constrained. [mscorlib]System.Guid
0x181b6  callvirt instance string [mscorlib]System.Object::ToString()
0x181bb  call     void Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddPropertyBagRelatedParamsAsInputVariable(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string channelPropertyGroupId)
0x181c0  ldloca.s 0x16
0x181c2  initobj  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x181c8  ldloca.s 0x16
0x181ca  ldc.i4.5
0x181cb  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_DataType(int32)
0x181d0  ldloca.s 0x16
0x181d2  ldstr    aResolvedsender// "ResolvedSenderReference"
0x181d7  ldc.i4.6
0x181d8  ldc.i4.1
0x181d9  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x181de  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Name(string)
0x181e3  ldloca.s 0x16
0x181e5  ldc.i4.0
0x181e6  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_IsMetadataBound(bool)
0x181eb  ldloca.s 0x16
0x181ed  ldsfld   valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::Empty
0x181f2  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_MetadataSource(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource)
0x181f7  ldloca.s 0x16
0x181f9  ldc.i4.0
0x181fa  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_HasValue(bool)
0x181ff  ldloc.s  0x16
0x18201  stloc.s  0xA
0x18203  ldloc.s  9
0x18205  ldloc.s  0xA
0x18207  call     string Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddParameterAsInputVariable(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition definition)
0x1820c  pop
0x1820d  ldloca.s 0x16
0x1820f  initobj  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x18215  ldloca.s 0x16
0x18217  ldc.i4.5
0x18218  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_DataType(int32)
0x1821d  ldloca.s 0x16
0x1821f  ldstr    aResolvedsender_0// "ResolvedSenderContactReference"
0x18224  ldc.i4.6
0x18225  ldc.i4.1
0x18226  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x1822b  call     instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Name(string)
  ... truncated ...
```
