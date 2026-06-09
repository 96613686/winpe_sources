# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetCustomActivityDataTypeInfo

- ea: `0x7e70`
- end: `0x7fda`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetCustomActivityDataTypeInfo`
- size: `362`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x49c0`
- `0x6ac0`
- `0x7e70`
- `0x89f0`

## pseudocode

```c

```

## disassembly

```asm
0x7e70  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7e75  stloc.0
0x7e76  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7e7b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7e80  ldarg.1
0x7e81  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7e86  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x7e8b  stloc.1
0x7e8c  ldarg.2
0x7e8d  ldstr    aInvokesdk// "InvokeSdk"
0x7e92  ldc.i4.5
0x7e93  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x7e98  brfalse  loc_7F37
0x7e9d  ldloc.1
0x7e9e  ldarg.2
0x7e9f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x7ea4  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep
0x7ea9  stloc.2
0x7eaa  ldarg.0
0x7eab  ldloc.2
0x7eac  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateInvokeSdkMessageCallStepParemeters(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageStep invokeSdkMessageStep)
0x7eb1  ldc.i4.0
0x7eb2  stloc.3
0x7eb3  ldloc.2
0x7eb4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x7eb9  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::GetEnumerator()
0x7ebe  stloc.s  4
0x7ec0  br.s     loc_7F0B
0x7ec2  ldloca.s 4
0x7ec4  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Current()
0x7ec9  stloc.s  5
0x7ecb  ldstr    aParametervalue// "ParameterValue"
0x7ed0  ldloca.s 3
0x7ed2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7ed7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x7edc  call     string [mscorlib]System.String::Concat(string, string)
0x7ee1  stloc.s  6
0x7ee3  ldarg.0
0x7ee4  ldloc.0
0x7ee5  ldloc.s  6
0x7ee7  ldloca.s 5
0x7ee9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Key()
0x7eee  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_WorkflowAttributeType()
0x7ef3  stloc.s  7
0x7ef5  ldloca.s 7
0x7ef7  constrained. [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType
0x7efd  callvirt instance string [mscorlib]System.Object::ToString()
0x7f02  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::AppendAttributeTypeInfo(class [mscorlib]System.Text.StringBuilder sb, string attributeName, string dataType)
0x7f07  ldloc.3
0x7f08  ldc.i4.1
0x7f09  add
0x7f0a  stloc.3
0x7f0b  ldloca.s 4
0x7f0d  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::MoveNext()
0x7f12  brtrue.s loc_7EC2
0x7f14  leave.s  loc_7F24
0x7f16  ldloca.s 4
0x7f18  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>
0x7f1e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7f23  endfinally
0x7f24  ldloc.0
0x7f25  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x7f2a  ldc.i4.0
0x7f2b  ble      loc_7FD4
0x7f30  ldloc.0
0x7f31  callvirt instance string [mscorlib]System.Object::ToString()
0x7f36  ret
0x7f37  ldloc.1
0x7f38  ldarg.2
0x7f39  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x7f3e  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityStep
0x7f43  stloc.s  8
0x7f45  ldarg.0
0x7f46  ldloc.s  8
0x7f48  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::UpdateCustomActivityStepPrameters(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityStep customActivityStep)
0x7f4d  ldc.i4.0
0x7f4e  stloc.s  9
0x7f50  ldloc.s  8
0x7f52  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Inputs()
0x7f57  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::GetEnumerator()
0x7f5c  stloc.s  4
0x7f5e  br.s     loc_7FAB
0x7f60  ldloca.s 4
0x7f62  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Current()
0x7f67  stloc.s  0xA
0x7f69  ldstr    aParametervalue// "ParameterValue"
0x7f6e  ldloca.s 9
0x7f70  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7f75  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x7f7a  call     string [mscorlib]System.String::Concat(string, string)
0x7f7f  stloc.s  0xB
0x7f81  ldarg.0
0x7f82  ldloc.0
0x7f83  ldloc.s  0xB
0x7f85  ldloca.s 0xA
0x7f87  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::get_Key()
0x7f8c  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_WorkflowAttributeType()
0x7f91  stloc.s  7
0x7f93  ldloca.s 7
0x7f95  constrained. [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType
0x7f9b  callvirt instance string [mscorlib]System.Object::ToString()
0x7fa0  call     instance void Microsoft.Crm.Application.WebServices.WorkflowWebService::AppendAttributeTypeInfo(class [mscorlib]System.Text.StringBuilder sb, string attributeName, string dataType)
0x7fa5  ldloc.s  9
0x7fa7  ldc.i4.1
0x7fa8  add
0x7fa9  stloc.s  9
0x7fab  ldloca.s 4
0x7fad  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::MoveNext()
0x7fb2  brtrue.s loc_7F60
0x7fb4  leave.s  loc_7FC4
0x7fb6  ldloca.s 4
0x7fb8  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>
0x7fbe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7fc3  endfinally
0x7fc4  ldloc.0
0x7fc5  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x7fca  ldc.i4.0
0x7fcb  ble.s    loc_7FD4
0x7fcd  ldloc.0
0x7fce  callvirt instance string [mscorlib]System.Object::ToString()
0x7fd3  ret
0x7fd4  ldstr    aNone// "None"
0x7fd9  ret
```
