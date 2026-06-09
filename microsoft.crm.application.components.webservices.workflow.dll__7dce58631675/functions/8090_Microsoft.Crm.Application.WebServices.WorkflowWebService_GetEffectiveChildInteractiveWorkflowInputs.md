# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetEffectiveChildInteractiveWorkflowInputs

- ea: `0x8090`
- end: `0x8187`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetEffectiveChildInteractiveWorkflowInputs`
- size: `247`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x28b0`
- `0x7fe0`

## callees

- `0x8090`

## pseudocode

```c

```

## disassembly

```asm
0x8090  ldarg.0
0x8091  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::get_ChildWorkflow()
0x8096  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression
0x809b  callvirt instance object [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::get_Value()
0x80a0  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression
0x80a5  callvirt instance object [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::get_Value()
0x80aa  unbox.any [mscorlib]System.Guid
0x80af  stloc.0
0x80b0  ldstr    aWorkflow// "workflow"
0x80b5  ldloc.0
0x80b6  ldc.i4.1
0x80b7  newarr   [mscorlib]System.String
0x80bc  dup
0x80bd  ldc.i4.0
0x80be  ldstr    aInputparameter// "inputparameters"
0x80c3  stelem.ref
0x80c4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x80c9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x80ce  stloc.1
0x80cf  ldloc.1
0x80d0  brtrue.s loc_80F6
0x80d2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x80d7  ldstr    aChildWorkflowW// "Child workflow with id {0} not found"
0x80dc  ldc.i4.1
0x80dd  newarr   [mscorlib]System.Object
0x80e2  dup
0x80e3  ldc.i4.0
0x80e4  ldloc.0
0x80e5  box      [mscorlib]System.Guid
0x80ea  stelem.ref
0x80eb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x80f0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x80f5  throw
0x80f6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor()
0x80fb  stloc.2
0x80fc  ldarg.0
0x80fd  ldloc.1
0x80fe  ldstr    aInputparameter// "inputparameters"
0x8103  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x8108  castclass [mscorlib]System.String
0x810d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::BuildNewInputParameterDictionary(string)
0x8112  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::GetEnumerator()
0x8117  stloc.3
0x8118  br.s     loc_816C
0x811a  ldloca.s 3
0x811c  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Current()
0x8121  stloc.s  4
0x8123  ldarg.0
0x8124  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::get_Inputs()
0x8129  ldloca.s 4
0x812b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Key()
0x8130  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::ContainsKey(var<u1>)
0x8135  brtrue.s loc_814D
0x8137  ldloc.2
0x8138  ldloca.s 4
0x813a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Key()
0x813f  ldloca.s 4
0x8141  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Value()
0x8146  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>, !!T0)
0x814b  br.s     loc_816C
0x814d  ldloc.2
0x814e  ldloca.s 4
0x8150  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Key()
0x8155  ldarg.0
0x8156  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep::get_Inputs()
0x815b  ldloca.s 4
0x815d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Key()
0x8162  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Item(void)
0x8167  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>, !!T0)
0x816c  ldloca.s 3
0x816e  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::MoveNext()
0x8173  brtrue.s loc_811A
0x8175  leave.s  loc_8185
0x8177  ldloca.s 3
0x8179  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>
0x817f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8184  endfinally
0x8185  ldloc.2
0x8186  ret
```
