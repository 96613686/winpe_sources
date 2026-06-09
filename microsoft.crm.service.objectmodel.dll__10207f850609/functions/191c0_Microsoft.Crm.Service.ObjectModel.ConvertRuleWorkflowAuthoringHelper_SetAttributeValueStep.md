# Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::SetAttributeValueStep

- ea: `0x191c0`
- end: `0x19249`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::SetAttributeValueStep`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18e90`

## callees

- `0x191c0`
- `0x19390`
- `0x193b0`

## pseudocode

```c

```

## disassembly

```asm
0x191c0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor()
0x191c5  stloc.0
0x191c6  ldnull
0x191c7  stloc.1
0x191c8  ldarg.2
0x191c9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap>::GetEnumerator()
0x191ce  stloc.2
0x191cf  br.s     loc_19233
0x191d1  ldloc.2
0x191d2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap>::get_Current()
0x191d7  stloc.3
0x191d8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor()
0x191dd  stloc.s  4
0x191df  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor()
0x191e4  stloc.s  5
0x191e6  ldarg.1
0x191e7  ldarg.3
0x191e8  ldstr    asc_2557C// "."
0x191ed  ldloc.3
0x191ee  callvirt instance string Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap::get_AssignedFrom()
0x191f3  call     string [mscorlib]System.String::Concat(string, string, string)
0x191f8  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.ExpressionBuilderHelper::CreateDynamicExpressionForValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x191fd  stloc.1
0x191fe  ldloc.s  4
0x19200  ldloc.1
0x19201  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>)
0x19206  ldarg.1
0x19207  ldc.i4.0
0x19208  ldloc.s  4
0x1920a  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::ToArray()
0x1920f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x19214  stloc.s  6
0x19216  ldloc.s  5
0x19218  ldloc.s  6
0x1921a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>)
0x1921f  ldloc.0
0x19220  ldloc.3
0x19221  callvirt instance string Microsoft.Crm.Service.ObjectModel.ConvertRuleAttributeMap::get_AssignedTo()
0x19226  ldloc.s  5
0x19228  ldc.i4.0
0x19229  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Item(!!T0)
0x1922e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>, !!T0)
0x19233  ldloc.2
0x19234  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19239  brtrue.s loc_191D1
0x1923b  leave.s  loc_19247
0x1923d  ldloc.2
0x1923e  brfalse.s loc_19246
0x19240  ldloc.2
0x19241  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19246  endfinally
0x19247  ldloc.0
0x19248  ret
```
