# Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::UpdateWorkflow

- ea: `0x169e0`
- end: `0x16af7`
- name: `Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::UpdateWorkflow`
- size: `279`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x169e0`
- `0x16ba0`
- `0x16c50`

## string_xrefs

- `0x16a44`: `applicablewhenxml`
- `0x16a7a`: `successconditionsxml`

## pseudocode

```c

```

## disassembly

```asm
0x169e0  ldarg.0
0x169e1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::get_WorkflowAdapter()
0x169e6  ldarg.0
0x169e7  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_workflowid
0x169ec  constrained. [mscorlib]System.Guid
0x169f2  callvirt instance string [mscorlib]System.Object::ToString()
0x169f7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x169fc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x16a01  stloc.0
0x16a02  ldarg.2
0x16a03  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0x16a08  ldstr    aWarnafter// "warnafter"
0x16a0d  callvirt instance bool [mscorlib]System.String::Contains(string)
0x16a12  brfalse.s loc_16A31
0x16a14  ldarg.0
0x16a15  ldarg.0
0x16a16  ldfld    bool Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_useslakpi
0x16a1b  brtrue.s loc_16A25
0x16a1d  ldarg.0
0x16a1e  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_updateWarningTimeoutStepId
0x16a23  br.s     loc_16A2B
0x16a25  ldarg.0
0x16a26  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_updateKPIWarningTimeoutStepId
0x16a2b  ldloc.0
0x16a2c  call     instance void Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::UpdateWaitTimeoutStep(string stepId, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x16a31  ldarg.0
0x16a32  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_applicableWhenXml
0x16a37  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16a3c  brtrue.s loc_16A67
0x16a3e  ldarg.2
0x16a3f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0x16a44  ldstr    aApplicablewhen// "applicablewhenxml"
0x16a49  callvirt instance bool [mscorlib]System.String::Contains(string)
0x16a4e  brfalse.s loc_16A67
0x16a50  ldarg.0
0x16a51  ldstr    aConditionbranc_5// "ConditionBranchStep2"
0x16a56  ldarg.0
0x16a57  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_applicableWhenXml
0x16a5c  ldloc.0
0x16a5d  ldstr    asc_1EEAE// ""
0x16a62  call     instance void Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::UpdateCondition(string activityId, string conditionXml, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x16a67  ldarg.0
0x16a68  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_successWhenStep
0x16a6d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16a72  brtrue.s loc_16AD8
0x16a74  ldarg.2
0x16a75  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Data()
0x16a7a  ldstr    aSuccessconditi// "successconditionsxml"
0x16a7f  callvirt instance bool [mscorlib]System.String::Contains(string)
0x16a84  brfalse.s loc_16AD8
0x16a86  ldarg.0
0x16a87  ldfld    bool Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_useslakpi
0x16a8c  brtrue.s loc_16A96
0x16a8e  ldarg.0
0x16a8f  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_updateSuccessCondtionSteps
0x16a94  br.s     loc_16A9C
0x16a96  ldarg.0
0x16a97  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_updateKPISuccessCondtionSteps
0x16a9c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x16aa1  stloc.1
0x16aa2  br.s     loc_16ABF
0x16aa4  ldloca.s 1
0x16aa6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x16aab  stloc.2
0x16aac  ldarg.0
0x16aad  ldloc.2
0x16aae  ldarg.0
0x16aaf  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_successWhenStep
0x16ab4  ldloc.0
0x16ab5  ldstr    asc_1EEAE// ""
0x16aba  call     instance void Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::UpdateCondition(string activityId, string conditionXml, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep, string descriptionXml)
0x16abf  ldloca.s 1
0x16ac1  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x16ac6  brtrue.s loc_16AA4
0x16ac8  leave.s  loc_16AD8
0x16aca  ldloca.s 1
0x16acc  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x16ad2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16ad7  endfinally
0x16ad8  ldloc.0
0x16ad9  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PublicationParameters()
0x16ade  ldstr    aSlaitem_0// "slaitem"
0x16ae3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowPublicationParameters::set_WorkflowRendererObjectTypeCode(string)
0x16ae8  ldarg.0
0x16ae9  ldloc.0
0x16aea  ldarg.1
0x16aeb  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAuthoringBase::Save(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext)
0x16af0  pop
0x16af1  leave.s  loc_16AF6
0x16af3  pop
0x16af4  rethrow
0x16af6  ret
```
