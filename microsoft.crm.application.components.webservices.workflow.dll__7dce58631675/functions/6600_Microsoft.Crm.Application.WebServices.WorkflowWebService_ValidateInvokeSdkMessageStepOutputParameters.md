# Microsoft.Crm.Application.WebServices.WorkflowWebService::ValidateInvokeSdkMessageStepOutputParameters

- ea: `0x6600`
- end: `0x6680`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::ValidateInvokeSdkMessageStepOutputParameters`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6360`

## callees

- `0x6600`

## pseudocode

```c

```

## disassembly

```asm
0x6600  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowErrorVisitorContext::.ctor()
0x6605  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Workflow.DataGenerator::.ctor()
0x660a  newobj   instance void [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorVisitor::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IUIDataGenerator)
0x660f  dup
0x6610  ldarg.1
0x6611  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepVisitorBase::VisitWorkflowStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x6616  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorTypes> [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorVisitor::get_ErrorMap()
0x661b  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorTypes>::GetEnumerator()
0x6620  stloc.0
0x6621  br.s     loc_6666
0x6623  ldloca.s 0
0x6625  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorTypes>::get_Current()
0x662a  stloc.1
0x662b  ldloca.s 1
0x662d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorTypes>::get_Key()
0x6632  ldstr    aInvokesdkmessa// "InvokeSdkMessageStep"
0x6637  ldc.i4.5
0x6638  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x663d  brfalse.s loc_6666
0x663f  ldloca.s 1
0x6641  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorTypes>::get_Value()
0x6646  ldc.i4.s 0x10
0x6648  and
0x6649  ldc.i4.0
0x664a  ble.s    loc_6666
0x664c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x6651  ldstr    aWebSfaWorkflow// "Web.SFA.Workflow.PerformAction.SaveFail"...
0x6656  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x665b  ldc.i4   0x80045014
0x6660  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x6665  throw
0x6666  ldloca.s 0
0x6668  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorTypes>::MoveNext()
0x666d  brtrue.s loc_6623
0x666f  leave.s  loc_667F
0x6671  ldloca.s 0
0x6673  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, valuetype [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.WorkflowErrorTypes>
0x6679  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x667e  endfinally
0x667f  ret
```
