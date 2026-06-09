# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertChildInteractiveWorkflowStep

- ea: `0x2820`
- end: `0x2872`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertChildInteractiveWorkflowStep`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x2820`
- `0x2880`
- `0x8b90`
- `0x8f00`
- `0x9170`

## pseudocode

```c

```

## disassembly

```asm
0x2820  ldarg.0
0x2821  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x2826  ldarg.2
0x2827  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x282c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x2831  stloc.0
0x2832  ldloc.0
0x2833  ldarg.1
0x2834  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x2839  ldarg.0
0x283a  ldloc.0
0x283b  ldarg.3
0x283c  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x2841  ldloc.0
0x2842  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x2847  stloc.1
0x2848  ldarg.0
0x2849  ldarg.s  4
0x284b  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x2850  ldloc.1
0x2851  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x2856  ldarg.0
0x2857  ldloc.1
0x2858  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetChildInteractiveWorkflowDefaultValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep childWorkflowStep)
0x285d  ldarg.0
0x285e  ldloc.0
0x285f  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x2864  stloc.2
0x2865  leave.s  loc_2870
0x2867  stloc.3
0x2868  ldarg.0
0x2869  ldloc.3
0x286a  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x286f  throw
0x2870  ldloc.2
0x2871  ret
```
