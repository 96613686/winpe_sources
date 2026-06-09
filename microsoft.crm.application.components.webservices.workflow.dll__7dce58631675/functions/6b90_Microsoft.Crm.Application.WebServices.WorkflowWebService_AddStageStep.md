# Microsoft.Crm.Application.WebServices.WorkflowWebService::AddStageStep

- ea: `0x6b90`
- end: `0x6c69`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::AddStageStep`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x6b90`
- `0x8b90`
- `0x8f00`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x6b90  ldarg.0
0x6b91  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x6b96  ldarg.2
0x6b97  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x6b9c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x6ba1  stloc.0
0x6ba2  ldarg.0
0x6ba3  ldloc.0
0x6ba4  ldarg.3
0x6ba5  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x6baa  ldloc.0
0x6bab  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6bb0  ldstr    aWebSfaWorkflow_0// "Web.SFA.Workflow.Stage"
0x6bb5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6bba  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x6bbf  stloc.1
0x6bc0  ldnull
0x6bc1  stloc.2
0x6bc2  ldc.i4.0
0x6bc3  stloc.3
0x6bc4  ldarg.1
0x6bc5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6bca  brtrue.s loc_6BFD
0x6bcc  ldloc.0
0x6bcd  ldarg.1
0x6bce  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x6bd3  stloc.2
0x6bd4  ldloc.2
0x6bd5  ldloc.0
0x6bd6  bne.un.s loc_6BF4
0x6bd8  ldnull
0x6bd9  stloc.2
0x6bda  br.s     loc_6BFD
0x6bdc  ldloc.2
0x6bdd  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x6be2  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep
0x6be7  brfalse.s loc_6BED
0x6be9  ldc.i4.1
0x6bea  stloc.3
0x6beb  br.s     loc_6BFD
0x6bed  ldloc.2
0x6bee  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x6bf3  stloc.2
0x6bf4  ldloc.2
0x6bf5  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x6bfa  ldloc.0
0x6bfb  bne.un.s loc_6BDC
0x6bfd  ldloc.3
0x6bfe  brfalse.s loc_6C12
0x6c00  ldloc.0
0x6c01  ldloc.1
0x6c02  ldloc.2
0x6c03  ldarg.0
0x6c04  ldarg.s  4
0x6c06  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x6c0b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::InsertStageStepWithChildPeer(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection)
0x6c10  br.s     loc_6C22
0x6c12  ldloc.0
0x6c13  ldloc.1
0x6c14  ldloc.2
0x6c15  ldarg.0
0x6c16  ldarg.s  4
0x6c18  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x6c1d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::InsertStageStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection)
0x6c22  ldloc.0
0x6c23  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x6c28  ldc.i4.0
0x6c29  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Item(int32)
0x6c2e  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep
0x6c33  brtrue.s loc_6C61
0x6c35  ldloc.0
0x6c36  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6c3b  ldstr    aWebSfaWorkflow_0// "Web.SFA.Workflow.Stage"
0x6c40  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x6c45  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StageStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x6c4a  stloc.s  4
0x6c4c  ldloc.0
0x6c4d  ldloc.s  4
0x6c4f  ldloc.0
0x6c50  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x6c55  ldc.i4.0
0x6c56  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Item(int32)
0x6c5b  ldc.i4.0
0x6c5c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::InsertStageStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection)
0x6c61  ldarg.0
0x6c62  ldloc.0
0x6c63  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x6c68  ret
```
