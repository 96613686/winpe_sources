# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertAssignEntityStep

- ea: `0x5300`
- end: `0x536d`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertAssignEntityStep`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x5300`
- `0x8ba0`
- `0x8f00`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x5300  ldarg.0
0x5301  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x5306  ldarg.2
0x5307  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x530c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x5311  stloc.0
0x5312  ldloc.0
0x5313  ldarg.1
0x5314  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x5319  ldarg.0
0x531a  ldloc.0
0x531b  ldarg.3
0x531c  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x5321  ldloc.0
0x5322  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x5327  stloc.1
0x5328  ldarg.0
0x5329  ldarg.s  4
0x532b  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x5330  ldloc.1
0x5331  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x5336  ldloc.1
0x5337  ldloc.1
0x5338  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.StepControlHelper::GetDefaultEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x533d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep::set_Entity(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase)
0x5342  ldarg.0
0x5343  ldloc.0
0x5344  ldarg.s  5
0x5346  dup
0x5347  brtrue.s loc_534F
0x5349  pop
0x534a  ldstr    asc_A26A// ""
0x534f  ldarg.s  6
0x5351  dup
0x5352  brtrue.s loc_535A
0x5354  pop
0x5355  ldstr    asc_A26A// ""
0x535a  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x535f  stloc.2
0x5360  leave.s  loc_536B
0x5362  stloc.3
0x5363  ldarg.0
0x5364  ldloc.3
0x5365  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x536a  throw
0x536b  ldloc.2
0x536c  ret
```
