# Microsoft.Crm.Application.WebServices.ProcessWebService::RetrieveConditionXmlFromExpression

- ea: `0x18a0`
- end: `0x1930`
- name: `Microsoft.Crm.Application.WebServices.ProcessWebService::RetrieveConditionXmlFromExpression`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18a0`
- `0x19b0`

## string_xrefs

- `0x18a1`: `workflowStepAsJson`

## pseudocode

```c

```

## disassembly

```asm
0x18a0  ldarg.1
0x18a1  ldstr    aWorkflowstepas// "workflowStepAsJson"
0x18a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x18ab  ldarg.2
0x18ac  ldstr    aStepid// "stepId"
0x18b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x18b6  ldarg.0
0x18b7  ldarg.1
0x18b8  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.WebServices.ProcessWebService::DeserializeJsonWorkflowStep(string jsonData)
0x18bd  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepDictionary [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_StepDictionary()
0x18c2  ldarg.2
0x18c3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Item(void)
0x18c8  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionBranchStep
0x18cd  stloc.0
0x18ce  ldloc.0
0x18cf  brtrue.s loc_18DC
0x18d1  ldstr    aNotValidStepFo// "Not valid step found"
0x18d6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x18db  throw
0x18dc  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x18e1  dup
0x18e2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18e7  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.Text.StringBuilder, class [mscorlib]System.IFormatProvider)
0x18ec  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.XmlSerializeExpressionVisitor::.ctor(class [mscorlib]System.IO.StringWriter)
0x18f1  stloc.1
0x18f2  ldloc.0
0x18f3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionBranchStep::get_ConditionExpression()
0x18f8  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.BinaryExpression
0x18fd  stloc.2
0x18fe  ldloc.2
0x18ff  brfalse.s loc_191D
0x1901  ldloc.2
0x1902  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.BinaryExpression::get_Operator()
0x1907  call     bool [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.OperatorClassifier::IsGroupingOperator(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator)
0x190c  brfalse.s loc_191D
0x190e  ldloc.1
0x190f  ldloc.2
0x1910  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.BinaryExpression::get_Operator()
0x1915  ldloc.2
0x1916  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.XmlSerializeExpressionVisitor::GroupExpressionAndVisit(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x191b  br.s     loc_192A
0x191d  ldloc.1
0x191e  ldc.i4.2
0x191f  ldloc.0
0x1920  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ConditionBranchStep::get_ConditionExpression()
0x1925  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.XmlSerializeExpressionVisitor::GroupExpressionAndVisit(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowConditionOperator, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x192a  callvirt instance string [mscorlib]System.Object::ToString()
0x192f  ret
```
