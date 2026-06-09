# Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertSendEmailStep

- ea: `0x5700`
- end: `0x5768`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::InsertSendEmailStep`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x5700`
- `0x8ba0`
- `0x8f00`
- `0x9170`
- `0x9200`

## pseudocode

```c

```

## disassembly

```asm
0x5700  ldarg.0
0x5701  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x5706  ldarg.2
0x5707  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x570c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x5711  stloc.0
0x5712  ldloc.0
0x5713  ldarg.1
0x5714  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x5719  ldarg.0
0x571a  ldloc.0
0x571b  ldarg.3
0x571c  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x5721  ldloc.0
0x5722  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x5727  stloc.1
0x5728  ldarg.0
0x5729  ldarg.s  4
0x572b  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection Microsoft.Crm.Application.WebServices.WorkflowWebService::GetDirectionEnum(string direction)
0x5730  ldloc.1
0x5731  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x5736  ldarg.0
0x5737  ldloc.1
0x5738  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetSendEmailDefaultValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep step)
0x573d  ldarg.0
0x573e  ldloc.0
0x573f  ldarg.s  5
0x5741  dup
0x5742  brtrue.s loc_574A
0x5744  pop
0x5745  ldstr    asc_A26A// ""
0x574a  ldarg.s  6
0x574c  dup
0x574d  brtrue.s loc_5755
0x574f  pop
0x5750  ldstr    asc_A26A// ""
0x5755  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string parentStepId, string rendererTypeCode)
0x575a  stloc.2
0x575b  leave.s  loc_5766
0x575d  stloc.3
0x575e  ldarg.0
0x575f  ldloc.3
0x5760  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x5765  throw
0x5766  ldloc.2
0x5767  ret
```
