# Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateInvokedMessageOfInvokeSdkMessageStep

- ea: `0x6100`
- end: `0x6193`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateInvokedMessageOfInvokeSdkMessageStep`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x6100`
- `0x6230`
- `0x6ac0`
- `0x8b90`
- `0x8f00`

## pseudocode

```c

```

## disassembly

```asm
0x6100  ldarg.0
0x6101  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x6106  ldarg.1
0x6107  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x610c  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x6111  stloc.0
0x6112  ldloc.0
0x6113  ldarg.3
0x6114  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x6119  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep
0x611e  stloc.1
0x611f  ldarg.0
0x6120  ldloc.0
0x6121  ldarg.2
0x6122  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateStepDescription(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x6127  ldloc.1
0x6128  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x612d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Clear()
0x6132  ldloc.1
0x6133  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Outputs()
0x6138  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase>::Clear()
0x613d  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::.ctor()
0x6142  stloc.2
0x6143  ldloca.s 3
0x6145  ldarg.s  4
0x6147  call     instance void [mscorlib]System.Guid::.ctor(string)
0x614c  ldloc.2
0x614d  ldloc.3
0x614e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::set_SdkMessageId(valuetype [mscorlib]System.Guid)
0x6153  ldarg.0
0x6154  ldloc.3
0x6155  ldloc.2
0x6156  ldstr    asc_A26A// ""
0x615b  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::SetSdkMessageDetails(valuetype [mscorlib]System.Guid sdkMessageId, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo objActivityInfo, [opt] string sdkMessageFilterId)
0x6160  ldloc.2
0x6161  ldloc.2
0x6162  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageActivityInfo::get_SdkMessageName()
0x6167  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::set_Name(string)
0x616c  ldloc.1
0x616d  ldloc.2
0x616e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::set_ActivityInfo(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase)
0x6173  ldarg.0
0x6174  ldloc.1
0x6175  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateInvokeSdkMessageCallStepParemeters(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep invokeSdkMessageStep)
0x617a  ldarg.0
0x617b  ldloc.0
0x617c  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::RenderWorkflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x6181  stloc.s  4
0x6183  leave.s  loc_6190
0x6185  stloc.s  5
0x6187  ldarg.0
0x6188  ldloc.s  5
0x618a  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x618f  throw
0x6190  ldloc.s  4
0x6192  ret
```
