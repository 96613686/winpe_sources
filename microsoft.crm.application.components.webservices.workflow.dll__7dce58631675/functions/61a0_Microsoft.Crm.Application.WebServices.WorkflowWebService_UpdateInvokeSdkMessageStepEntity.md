# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateInvokeSdkMessageStepEntity

- ea: `0x61a0`
- end: `0x6230`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateInvokeSdkMessageStepEntity`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x61a0`
- `0x6230`
- `0x6ac0`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x61a0  ldarg.0
0x61a1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x61a6  ldarg.1
0x61a7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x61ac  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x61b1  stloc.0
0x61b2  ldloc.0
0x61b3  ldarg.3
0x61b4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x61b9  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep
0x61be  stloc.1
0x61bf  ldarg.0
0x61c0  ldloc.0
0x61c1  ldarg.2
0x61c2  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x61c7  ldloc.1
0x61c8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x61cd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Clear()
0x61d2  ldloc.1
0x61d3  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Outputs()
0x61d8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase>::Clear()
0x61dd  ldarg.0
0x61de  ldloc.1
0x61df  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateInvokeSdkMessageCallStepParemeters(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep invokeSdkMessageStep)
0x61e4  ldloca.s 2
0x61e6  ldarg.s  4
0x61e8  call     instance void [mscorlib]System.Guid::.ctor(string)
0x61ed  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::.ctor()
0x61f2  stloc.3
0x61f3  ldarg.0
0x61f4  ldloc.2
0x61f5  ldloc.3
0x61f6  ldarg.s  5
0x61f8  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetSdkMessageDetails(valuetype [mscorlib]System.Guid sdkMessageId, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo objActivityInfo, [opt] string sdkMessageFilterId)
0x61fd  ldloc.3
0x61fe  ldloc.3
0x61ff  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::get_SdkMessageName()
0x6204  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::set_Name(string)
0x6209  ldloc.3
0x620a  ldloc.2
0x620b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::set_SdkMessageId(valuetype [mscorlib]System.Guid)
0x6210  ldloc.1
0x6211  ldloc.3
0x6212  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::set_ActivityInfo(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase)
0x6217  ldarg.0
0x6218  ldloc.0
0x6219  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x621e  stloc.s  4
0x6220  leave.s  loc_622D
0x6222  stloc.s  5
0x6224  ldarg.0
0x6225  ldloc.s  5
0x6227  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x622c  throw
0x622d  ldloc.s  4
0x622f  ret
```
