# Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::CreateInteractionPage

- ea: `0x2bbd0`
- end: `0x2bd02`
- name: `Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::CreateInteractionPage`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x26b10`

## callees

- `0x29e50`
- `0x2b7f0`
- `0x2bbd0`
- `0x2e050`
- `0x2e060`
- `0x2e080`
- `0x2e0c0`

## pseudocode

```c

```

## disassembly

```asm
0x2bbd0  newobj   instance void Microsoft.Crm.Workflow.Activities.InteractionPage::.ctor()
0x2bbd5  dup
0x2bbd6  ldarg.1
0x2bbd7  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Id()
0x2bbdc  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2bbe1  dup
0x2bbe2  ldarg.2
0x2bbe3  newobj   instance void class [System.Activities]System.Activities.InArgument`1<bool>::.ctor(var<u1>)
0x2bbe8  callvirt instance void Microsoft.Crm.Workflow.Activities.InteractionPage::set_AllowBack(class [System.Activities]System.Activities.InArgument`1<bool> value)
0x2bbed  stloc.0
0x2bbee  ldarg.1
0x2bbef  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x2bbf4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2bbf9  brtrue.s loc_2BC17
0x2bbfb  ldloc.0
0x2bbfc  dup
0x2bbfd  callvirt instance string [System.Activities]System.Activities.Activity::get_DisplayName()
0x2bc02  ldstr    asc_3C24E// ": "
0x2bc07  ldarg.1
0x2bc08  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Description()
0x2bc0d  call     string [mscorlib]System.String::Concat(string, string, string)
0x2bc12  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x2bc17  ldarg.0
0x2bc18  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2bc1d  stloc.1
0x2bc1e  ldarg.0
0x2bc1f  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2bc24  stloc.2
0x2bc25  ldarg.0
0x2bc26  ldloc.0
0x2bc27  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.InteractionPage::get_Activities()
0x2bc2c  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2bc31  ldarg.0
0x2bc32  ldloc.0
0x2bc33  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.Activities.InteractionPage::get_Variables()
0x2bc38  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2bc3d  ldarg.0
0x2bc3e  ldarg.1
0x2bc3f  call     instance void Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::VisitChildren(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase step)
0x2bc44  ldarg.0
0x2bc45  ldloc.1
0x2bc46  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2bc4b  ldarg.0
0x2bc4c  ldloc.2
0x2bc4d  stfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentVariables
0x2bc52  ldloc.0
0x2bc53  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable> Microsoft.Crm.Workflow.Activities.InteractionPage::get_Variables()
0x2bc58  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::GetEnumerator()
0x2bc5d  stloc.s  4
0x2bc5f  br.s     loc_2BCD6
0x2bc61  ldloc.s  4
0x2bc63  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Activities]System.Activities.Variable>::get_Current()
0x2bc68  callvirt instance string [System.Activities]System.Activities.Variable::get_Name()
0x2bc6d  stloc.s  5
0x2bc6f  ldloc.s  5
0x2bc71  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::InteractionResponseVariableNameSuffix
0x2bc76  ldc.i4.4
0x2bc77  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x2bc7c  brfalse.s loc_2BCD6
0x2bc7e  newobj   instance void class [System.Activities]System.Activities.Statements.Assign`1<class Microsoft.Crm.Workflow.InteractionActivityResult>::.ctor()
0x2bc83  dup
0x2bc84  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class Microsoft.Crm.Workflow.InteractionActivityResult>::.ctor()
0x2bc89  dup
0x2bc8a  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::InteractionResponsesVariableName
0x2bc8f  ldstr    asc_3C35A// "(\""
0x2bc94  ldloc.s  5
0x2bc96  ldstr    asc_3C360// "\")"
0x2bc9b  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x2bca0  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicReference`1<class Microsoft.Crm.Workflow.InteractionActivityResult>::set_ExpressionText(string)
0x2bca5  newobj   instance void class [System.Activities]System.Activities.OutArgument`1<class Microsoft.Crm.Workflow.InteractionActivityResult>::.ctor(class [System.Activities]System.Activities.Activity`1<class [System.Activities]System.Activities.Location`1<var<u1>>>)
0x2bcaa  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<class Microsoft.Crm.Workflow.InteractionActivityResult>::set_To(class [System.Activities]System.Activities.OutArgument`1<var<u1>>)
0x2bcaf  dup
0x2bcb0  newobj   instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class Microsoft.Crm.Workflow.InteractionActivityResult>::.ctor()
0x2bcb5  dup
0x2bcb6  ldloc.s  5
0x2bcb8  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class Microsoft.Crm.Workflow.InteractionActivityResult>::set_ExpressionText(string)
0x2bcbd  call     class [System.Activities]System.Activities.InArgument`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<class Microsoft.Crm.Workflow.InteractionActivityResult>::op_Implicit(!!T0)
0x2bcc2  callvirt instance void class [System.Activities]System.Activities.Statements.Assign`1<class Microsoft.Crm.Workflow.InteractionActivityResult>::set_Value(class [System.Activities]System.Activities.InArgument`1<var<u1>>)
0x2bcc7  stloc.s  6
0x2bcc9  ldloc.0
0x2bcca  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.Activities.InteractionPage::get_Activities()
0x2bccf  ldloc.s  6
0x2bcd1  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x2bcd6  ldloc.s  4
0x2bcd8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2bcdd  brtrue.s loc_2BC61
0x2bcdf  leave.s  loc_2BCED
0x2bce1  ldloc.s  4
0x2bce3  brfalse.s loc_2BCEC
0x2bce5  ldloc.s  4
0x2bce7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2bcec  endfinally
0x2bced  ldarg.0
0x2bcee  ldloc.0
0x2bcef  call     instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.ActivityReference Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::ReferenceActivity(class [System.Activities]System.Activities.Activity activity)
0x2bcf4  stloc.3
0x2bcf5  ldarg.0
0x2bcf6  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::_parentActivities
0x2bcfb  ldloc.3
0x2bcfc  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::Add(var<u1>)
0x2bd01  ret
```
