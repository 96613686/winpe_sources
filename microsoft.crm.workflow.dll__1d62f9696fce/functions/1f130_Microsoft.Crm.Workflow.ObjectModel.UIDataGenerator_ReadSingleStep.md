# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSingleStep

- ea: `0x1f130`
- end: `0x1f294`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSingleStep`
- size: `356`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1ea20`
- `0x1f610`
- `0x202c0`
- `0x21830`
- `0x219c0`

## callees

- `0x1ee70`
- `0x1f130`
- `0x1f2a0`
- `0x1f660`
- `0x1fc10`
- `0x1fd10`
- `0x22480`
- `0x22f90`
- `0x23920`
- `0x2e2f0`

## pseudocode

```c

```

## disassembly

```asm
0x1f130  ldnull
0x1f131  stloc.0
0x1f132  ldnull
0x1f133  stloc.1
0x1f134  ldarg.1
0x1f135  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x1f13a  ldloca.s 0
0x1f13c  ldloca.s 1
0x1f13e  call     void Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ExtractStepIdAndDescription(string displayName, [out] string& stepId, [out] string& description)
0x1f143  ldnull
0x1f144  stloc.2
0x1f145  ldarg.1
0x1f146  isinst   [System.Activities]System.Activities.Statements.Sequence
0x1f14b  dup
0x1f14c  stloc.3
0x1f14d  brfalse.s loc_1F171
0x1f14f  ldarg.1
0x1f150  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x1f155  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f15a  brtrue.s loc_1F171
0x1f15c  ldarg.0
0x1f15d  ldloc.0
0x1f15e  ldloc.1
0x1f15f  ldarg.1
0x1f160  ldloc.3
0x1f161  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> [System.Activities]System.Activities.Statements.Sequence::get_Variables()
0x1f166  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCompositeStep(string stepId, string description, class [System.Activities]System.Activities.Activity activity, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> variables)
0x1f16b  stloc.2
0x1f16c  br       loc_1F24B
0x1f171  ldarg.1
0x1f172  isinst   Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity
0x1f177  dup
0x1f178  stloc.s  5
0x1f17a  brfalse.s loc_1F1B0
0x1f17c  ldarg.0
0x1f17d  ldloc.s  5
0x1f17f  call     instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::DereferenceActivityForInvokeSdkMessage(class [System.Activities]System.Activities.Activity activity)
0x1f184  stloc.s  0xA
0x1f186  ldloc.s  5
0x1f188  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x1f18d  ldstr    aVariables// "Variables"
0x1f192  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x1f197  isinst   class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>
0x1f19c  stloc.s  0xB
0x1f19e  ldarg.0
0x1f19f  ldloc.0
0x1f1a0  ldloc.1
0x1f1a1  ldloc.s  0xA
0x1f1a3  ldloc.s  0xB
0x1f1a5  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCompositeStep(string stepId, string description, class [System.Activities]System.Activities.Activity activity, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> variables)
0x1f1aa  stloc.2
0x1f1ab  br       loc_1F24B
0x1f1b0  ldarg.1
0x1f1b1  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference
0x1f1b6  dup
0x1f1b7  stloc.s  4
0x1f1b9  brfalse.s loc_1F1F9
0x1f1bb  ldarg.1
0x1f1bc  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x1f1c1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f1c6  brtrue.s loc_1F1F9
0x1f1c8  ldarg.0
0x1f1c9  ldloc.s  4
0x1f1cb  call     instance class [System.Activities]System.Activities.Activity Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::DereferenceActivity(class [System.Activities]System.Activities.Activity activity)
0x1f1d0  stloc.s  0xC
0x1f1d2  ldloc.s  4
0x1f1d4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReferenceBase::get_Properties()
0x1f1d9  ldstr    aVariables// "Variables"
0x1f1de  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x1f1e3  isinst   class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>
0x1f1e8  stloc.s  0xD
0x1f1ea  ldarg.0
0x1f1eb  ldloc.0
0x1f1ec  ldloc.1
0x1f1ed  ldloc.s  0xC
0x1f1ef  ldloc.s  0xD
0x1f1f1  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadCompositeStep(string stepId, string description, class [System.Activities]System.Activities.Activity activity, class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> variables)
0x1f1f6  stloc.2
0x1f1f7  br.s     loc_1F24B
0x1f1f9  ldarg.1
0x1f1fa  isinst   [System.Activities]System.Activities.Statements.TerminateWorkflow
0x1f1ff  dup
0x1f200  stloc.s  6
0x1f202  brfalse.s loc_1F20F
0x1f204  ldarg.0
0x1f205  ldloc.s  6
0x1f207  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStopWorkflowStep(class [System.Activities]System.Activities.Statements.TerminateWorkflow activity)
0x1f20c  stloc.2
0x1f20d  br.s     loc_1F24B
0x1f20f  ldarg.1
0x1f210  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SetState
0x1f215  dup
0x1f216  stloc.s  7
0x1f218  brfalse.s loc_1F225
0x1f21a  ldarg.0
0x1f21b  ldloc.s  7
0x1f21d  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSetStateStep(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SetState activity)
0x1f222  stloc.2
0x1f223  br.s     loc_1F24B
0x1f225  ldarg.1
0x1f226  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.StartChildWorkflow
0x1f22b  dup
0x1f22c  stloc.s  8
0x1f22e  brfalse.s loc_1F23B
0x1f230  ldarg.0
0x1f231  ldloc.s  8
0x1f233  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStartChildWorkflowStep(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.StartChildWorkflow activity)
0x1f238  stloc.2
0x1f239  br.s     loc_1F24B
0x1f23b  ldstr    aWorkflowContai// "Workflow contains unexpected activity."
0x1f240  ldc.i4   0x80040216
0x1f245  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1f24a  throw
0x1f24b  ldarg.0
0x1f24c  ldloc.0
0x1f24d  call     instance int32 Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::FindStepNumber(string stepId)
0x1f252  stloc.s  9
0x1f254  ldloc.s  9
0x1f256  ldarg.0
0x1f257  ldfld    int32 Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_lastStepId
0x1f25c  ble.s    loc_1F266
0x1f25e  ldarg.0
0x1f25f  ldloc.s  9
0x1f261  stfld    int32 Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_lastStepId
0x1f266  ldloc.2
0x1f267  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f26c  ldstr    a0// "{0}"
0x1f271  ldc.i4.1
0x1f272  newarr   [mscorlib]System.Object
0x1f277  dup
0x1f278  ldc.i4.0
0x1f279  ldloc.s  9
0x1f27b  box      [mscorlib]System.Int32
0x1f280  stelem.ref
0x1f281  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1f286  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::SetNameAndId(string)
0x1f28b  ldloc.2
0x1f28c  ldloc.1
0x1f28d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::set_Description(string)
0x1f292  ldloc.2
0x1f293  ret
```
