# Microsoft.Crm.Application.WebServices.WorkflowWebService::CopyWorkflowStep

- ea: `0x81f0`
- end: `0x8252`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::CopyWorkflowStep`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x81f0`
- `0x8260`
- `0x8b90`

## pseudocode

```c

```

## disassembly

```asm
0x81f0  ldarg.0
0x81f1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x81f6  ldarg.1
0x81f7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x81fc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x8201  stloc.0
0x8202  ldloc.0
0x8203  ldarg.2
0x8204  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x8209  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x820e  stloc.1
0x820f  ldarg.3
0x8210  stloc.2
0x8211  ldc.i4.0
0x8212  stloc.3
0x8213  br.s     loc_8233
0x8215  ldloc.2
0x8216  ldloc.3
0x8217  ldelem.ref
0x8218  stloc.s  4
0x821a  ldarg.0
0x821b  ldloc.0
0x821c  ldloc.1
0x821d  ldloc.0
0x821e  ldloc.s  4
0x8220  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x8225  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x822a  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::CopyWorkflowSteps(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase srcCompStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase destCompStep)
0x822f  ldloc.3
0x8230  ldc.i4.1
0x8231  add
0x8232  stloc.3
0x8233  ldloc.3
0x8234  ldloc.2
0x8235  ldlen
0x8236  conv.i4
0x8237  blt.s    loc_8215
0x8239  ldarg.0
0x823a  ldloc.0
0x823b  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x8240  stloc.s  5
0x8242  leave.s  loc_824F
0x8244  stloc.s  6
0x8246  ldarg.0
0x8247  ldloc.s  6
0x8249  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x824e  throw
0x824f  ldloc.s  5
0x8251  ret
```
