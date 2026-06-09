# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetChildInteractiveWorkflowDataTypeInfo

- ea: `0x7fe0`
- end: `0x808c`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetChildInteractiveWorkflowDataTypeInfo`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x7fe0`
- `0x8090`
- `0x89f0`

## pseudocode

```c

```

## disassembly

```asm
0x7fe0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7fe5  stloc.0
0x7fe6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7feb  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7ff0  ldarg.1
0x7ff1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7ff6  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x7ffb  ldarg.2
0x7ffc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x8001  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep
0x8006  ldc.i4.0
0x8007  stloc.1
0x8008  call     class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> Microsoft.Crm.Application.WebServices.WorkflowWebService::GetEffectiveChildInteractiveWorkflowInputs(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildInteractiveWorkflowStep childInteractiveWorkflowStep)
0x800d  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::GetEnumerator()
0x8012  stloc.2
0x8013  br.s     loc_805D
0x8015  ldloca.s 2
0x8017  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Current()
0x801c  stloc.3
0x801d  ldstr    aParametervalue// "ParameterValue"
0x8022  ldloca.s 1
0x8024  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8029  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x802e  call     string [mscorlib]System.String::Concat(string, string)
0x8033  stloc.s  4
0x8035  ldarg.0
0x8036  ldloc.0
0x8037  ldloc.s  4
0x8039  ldloca.s 3
0x803b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Key()
0x8040  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_WorkflowAttributeType()
0x8045  stloc.s  5
0x8047  ldloca.s 5
0x8049  constrained. [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType
0x804f  callvirt instance string [mscorlib]System.Object::ToString()
0x8054  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::AppendAttributeTypeInfo(class [mscorlib]System.Text.StringBuilder sb, string attributeName, string dataType)
0x8059  ldloc.1
0x805a  ldc.i4.1
0x805b  add
0x805c  stloc.1
0x805d  ldloca.s 2
0x805f  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::MoveNext()
0x8064  brtrue.s loc_8015
0x8066  leave.s  loc_8076
0x8068  ldloca.s 2
0x806a  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>
0x8070  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8075  endfinally
0x8076  ldloc.0
0x8077  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x807c  ldc.i4.0
0x807d  ble.s    loc_8086
0x807f  ldloc.0
0x8080  callvirt instance string [mscorlib]System.Object::ToString()
0x8085  ret
0x8086  ldstr    aNone// "None"
0x808b  ret
```
