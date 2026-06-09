# Microsoft.Crm.Application.WebServices.WorkflowWebService::CopyWorkflowSteps

- ea: `0x8260`
- end: `0x834d`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::CopyWorkflowSteps`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x81f0`

## callees

- `0x8260`
- `0x8350`

## pseudocode

```c

```

## disassembly

```asm
0x8260  br.s     loc_8274
0x8262  ldarg.3
0x8263  ldarg.3
0x8264  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x8269  ldc.i4.0
0x826a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Item(int32)
0x826f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::Remove(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x8274  ldarg.3
0x8275  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x827a  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::get_Count()
0x827f  ldc.i4.0
0x8280  bgt.s    loc_8262
0x8282  ldarg.2
0x8283  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::get_Steps()
0x8288  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepCollection::GetEnumerator()
0x828d  stloc.0
0x828e  br       loc_8335
0x8293  ldloc.0
0x8294  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Current()
0x8299  stloc.1
0x829a  ldloc.1
0x829b  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::CloneSteps()
0x82a0  stloc.2
0x82a1  ldarg.1
0x82a2  dup
0x82a3  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_NextStepIndex()
0x82a8  stloc.s  4
0x82aa  ldloc.s  4
0x82ac  ldc.i4.1
0x82ad  add
0x82ae  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::set_NextStepIndex(int32)
0x82b3  ldloca.s 4
0x82b5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x82ba  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x82bf  stloc.3
0x82c0  ldloc.2
0x82c1  ldarg.0
0x82c2  ldloc.1
0x82c3  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x82c8  ldstr    aStep// "Step"
0x82cd  ldloc.3
0x82ce  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::InjectNewStepId(string Id, string Identifier, string NewStepId)
0x82d3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Id(string)
0x82d8  ldloc.2
0x82d9  ldarg.0
0x82da  ldloc.1
0x82db  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Name()
0x82e0  ldstr    aStep_0// "Step_"
0x82e5  ldloc.3
0x82e6  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::InjectNewStepId(string Id, string Identifier, string NewStepId)
0x82eb  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Name(string)
0x82f0  ldloc.1
0x82f1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_StepLabels()
0x82f6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabelCollection::GetEnumerator()
0x82fb  stloc.s  5
0x82fd  br.s     loc_8317
0x82ff  ldloc.s  5
0x8301  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel>::get_Current()
0x8306  dup
0x8307  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::get_LabelId()
0x830c  ldloc.3
0x830d  call     string [mscorlib]System.String::Concat(string, string)
0x8312  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepLabel::set_LabelId(string)
0x8317  ldloc.s  5
0x8319  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x831e  brtrue.s loc_82FF
0x8320  leave.s  loc_832E
0x8322  ldloc.s  5
0x8324  brfalse.s loc_832D
0x8326  ldloc.s  5
0x8328  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x832d  endfinally
0x832e  ldarg.3
0x832f  ldloc.2
0x8330  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x8335  ldloc.0
0x8336  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x833b  brtrue   loc_8293
0x8340  leave.s  loc_834C
0x8342  ldloc.0
0x8343  brfalse.s loc_834B
0x8345  ldloc.0
0x8346  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x834b  endfinally
0x834c  ret
```
