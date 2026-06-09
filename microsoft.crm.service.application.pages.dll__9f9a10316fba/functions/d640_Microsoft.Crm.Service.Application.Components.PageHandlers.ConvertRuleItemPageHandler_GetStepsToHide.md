# Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::GetStepsToHide

- ea: `0xd640`
- end: `0xd6c6`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::GetStepsToHide`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xd240`

## callees

- `0xd640`

## pseudocode

```c

```

## disassembly

```asm
0xd640  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0xd645  stloc.0
0xd646  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd64b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd650  ldarg.1
0xd651  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xd656  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0xd65b  ldstr    aConditionbranc_2// "ConditionBranchStep2"
0xd660  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0xd665  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0xd66a  stloc.1
0xd66b  ldloc.1
0xd66c  brfalse.s loc_D6BF
0xd66e  ldloc.1
0xd66f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0xd674  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::GetEnumerator()
0xd679  stloc.2
0xd67a  br.s     loc_D6AB
0xd67c  ldloc.2
0xd67d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Current()
0xd682  stloc.3
0xd683  ldloc.3
0xd684  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep
0xd689  brfalse.s loc_D697
0xd68b  ldloc.0
0xd68c  ldloc.3
0xd68d  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0xd692  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xd697  ldloc.3
0xd698  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SendEmailStep
0xd69d  brfalse.s loc_D6AB
0xd69f  ldloc.0
0xd6a0  ldloc.3
0xd6a1  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0xd6a6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xd6ab  ldloc.2
0xd6ac  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xd6b1  brtrue.s loc_D67C
0xd6b3  leave.s  loc_D6BF
0xd6b5  ldloc.2
0xd6b6  brfalse.s loc_D6BE
0xd6b8  ldloc.2
0xd6b9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd6be  endfinally
0xd6bf  ldloc.0
0xd6c0  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0xd6c5  ret
```
