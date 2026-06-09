# Microsoft.Crm.Workflow.Services.SetMessageService::ExecuteInternal

- ea: `0x19d30`
- end: `0x19e07`
- name: `Microsoft.Crm.Workflow.Services.SetMessageService::ExecuteInternal`
- size: `215`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x19d20`

## callees

- `0x109a0`
- `0x14770`
- `0x14ee0`
- `0x19d30`
- `0x1abc0`

## pseudocode

```c

```

## disassembly

```asm
0x19d30  ldarg.0
0x19d31  call     instance bool Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_IsSynchronousWorkflowRuntime()
0x19d36  brtrue.s loc_19D92
0x19d38  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x19d3d  ldarg.0
0x19d3e  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x19d43  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x19d48  ldarg.0
0x19d49  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x19d4e  castclass [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext
0x19d53  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x19d58  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x19d5d  stloc.0
0x19d5e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache::Instance()
0x19d63  ldloc.0
0x19d64  ldarg.1
0x19d65  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel> Microsoft.Crm.Workflow.ClientActivities.SetMessage::get_StepLabels()
0x19d6a  ldc.i4.0
0x19d6b  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel>::get_Item(!!T0)
0x19d70  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::get_LabelId()
0x19d75  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x19d7a  ldstr    aDescription// "description"
0x19d7f  ldarg.0
0x19d80  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x19d85  castclass [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext
0x19d8a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache::TryLookupEntry(int32, valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19d8f  stloc.1
0x19d90  br.s     loc_19DDF
0x19d92  ldarg.0
0x19d93  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x19d98  castclass Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext
0x19d9d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::get_ExecutionContext()
0x19da2  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerLanguageCode()
0x19da7  stloc.0
0x19da8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache::Instance()
0x19dad  ldloc.0
0x19dae  ldarg.1
0x19daf  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel> Microsoft.Crm.Workflow.ClientActivities.SetMessage::get_StepLabels()
0x19db4  ldc.i4.0
0x19db5  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel>::get_Item(!!T0)
0x19dba  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::get_LabelId()
0x19dbf  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x19dc4  ldstr    aDescription// "description"
0x19dc9  ldarg.0
0x19dca  call     instance class Microsoft.Crm.Workflow.ICommonWorkflowContext Microsoft.Crm.Workflow.Services.ActivityServiceBase::get_WorkflowContext()
0x19dcf  castclass Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext
0x19dd4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Workflow.SynchronousRuntime.SynchronousWorkflowContext::get_ExecutionContext()
0x19dd9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCache::TryLookupEntry(int32, valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19dde  stloc.1
0x19ddf  ldloc.1
0x19de0  brfalse.s loc_19DEF
0x19de2  ldc.i4.1
0x19de3  ldloc.1
0x19de4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0x19de9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException::.ctor(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OperationStatus, string)
0x19dee  throw
0x19def  ldc.i4.1
0x19df0  ldarg.1
0x19df1  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel> Microsoft.Crm.Workflow.ClientActivities.SetMessage::get_StepLabels()
0x19df6  ldc.i4.0
0x19df7  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel>::get_Item(!!T0)
0x19dfc  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::get_Description()
0x19e01  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.InvalidPluginExecutionException::.ctor(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OperationStatus, string)
0x19e06  throw
```
