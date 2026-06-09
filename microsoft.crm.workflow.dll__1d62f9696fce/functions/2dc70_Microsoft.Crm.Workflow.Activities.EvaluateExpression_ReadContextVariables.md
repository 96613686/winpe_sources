# Microsoft.Crm.Workflow.Activities.EvaluateExpression::ReadContextVariables

- ea: `0x2dc70`
- end: `0x2dd62`
- name: `Microsoft.Crm.Workflow.Activities.EvaluateExpression::ReadContextVariables`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x2dbb0`

## callees

- `0x2db50`
- `0x2db70`
- `0x2db90`
- `0x2dc70`

## pseudocode

```c

```

## disassembly

```asm
0x2dc70  ldarg.1
0x2dc71  callvirt instance class [System.Activities]System.Activities.WorkflowDataContext [System.Activities]System.Activities.ActivityContext::get_DataContext()
0x2dc76  callvirt instance class [System]System.ComponentModel.PropertyDescriptorCollection [System]System.ComponentModel.CustomTypeDescriptor::GetProperties()
0x2dc7b  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.ComponentModel.PropertyDescriptorCollection::GetEnumerator()
0x2dc80  stloc.0
0x2dc81  br       loc_2DD40
0x2dc86  ldloc.0
0x2dc87  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2dc8c  castclass [System]System.ComponentModel.PropertyDescriptor
0x2dc91  stloc.1
0x2dc92  ldnull
0x2dc93  stloc.2
0x2dc94  ldloc.1
0x2dc95  callvirt instance string [System]System.ComponentModel.MemberDescriptor::get_Name()
0x2dc9a  stloc.3
0x2dc9b  ldloc.3
0x2dc9c  ldstr    aSteplabellangu// "stepLabelLanguageCode"
0x2dca1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dca6  brtrue.s loc_2DCC4
0x2dca8  ldloc.3
0x2dca9  ldstr    aSteplabeldescr// "stepLabelDescription"
0x2dcae  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dcb3  brtrue.s loc_2DCEA
0x2dcb5  ldloc.3
0x2dcb6  ldstr    aSteplabellabel// "stepLabelLabelId"
0x2dcbb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2dcc0  brtrue.s loc_2DD0D
0x2dcc2  br.s     loc_2DD40
0x2dcc4  ldloc.1
0x2dcc5  ldarg.1
0x2dcc6  callvirt instance class [System.Activities]System.Activities.WorkflowDataContext [System.Activities]System.Activities.ActivityContext::get_DataContext()
0x2dccb  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x2dcd0  stloc.2
0x2dcd1  ldloc.2
0x2dcd2  brfalse.s loc_2DD40
0x2dcd4  ldloc.2
0x2dcd5  isinst   [mscorlib]System.Int32
0x2dcda  brfalse.s loc_2DD40
0x2dcdc  ldarg.0
0x2dcdd  ldloc.2
0x2dcde  unbox.any [mscorlib]System.Int32
0x2dce3  call     instance void Microsoft.Crm.Workflow.Activities.EvaluateExpression::set_StepLabelLanguageCode(int32 value)
0x2dce8  br.s     loc_2DD40
0x2dcea  ldloc.1
0x2dceb  ldarg.1
0x2dcec  callvirt instance class [System.Activities]System.Activities.WorkflowDataContext [System.Activities]System.Activities.ActivityContext::get_DataContext()
0x2dcf1  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x2dcf6  stloc.2
0x2dcf7  ldloc.2
0x2dcf8  isinst   [mscorlib]System.String
0x2dcfd  stloc.s  4
0x2dcff  ldloc.s  4
0x2dd01  brfalse.s loc_2DD40
0x2dd03  ldarg.0
0x2dd04  ldloc.s  4
0x2dd06  call     instance void Microsoft.Crm.Workflow.Activities.EvaluateExpression::set_StepLabelDescription(string value)
0x2dd0b  br.s     loc_2DD40
0x2dd0d  ldloc.1
0x2dd0e  ldarg.1
0x2dd0f  callvirt instance class [System.Activities]System.Activities.WorkflowDataContext [System.Activities]System.Activities.ActivityContext::get_DataContext()
0x2dd14  callvirt instance object [System]System.ComponentModel.PropertyDescriptor::GetValue(object)
0x2dd19  stloc.2
0x2dd1a  ldloc.2
0x2dd1b  isinst   [mscorlib]System.String
0x2dd20  stloc.s  5
0x2dd22  ldloc.s  5
0x2dd24  brfalse.s loc_2DD40
0x2dd26  ldarg.0
0x2dd27  ldloc.s  5
0x2dd29  ldloca.s 6
0x2dd2b  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x2dd30  brtrue.s loc_2DD39
0x2dd32  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2dd37  br.s     loc_2DD3B
0x2dd39  ldloc.s  6
0x2dd3b  call     instance void Microsoft.Crm.Workflow.Activities.EvaluateExpression::set_StepLabelLabelId(valuetype [mscorlib]System.Guid value)
0x2dd40  ldloc.0
0x2dd41  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2dd46  brtrue   loc_2DC86
0x2dd4b  leave.s  loc_2DD61
0x2dd4d  ldloc.0
0x2dd4e  isinst   [mscorlib]System.IDisposable
0x2dd53  stloc.s  7
0x2dd55  ldloc.s  7
0x2dd57  brfalse.s loc_2DD60
0x2dd59  ldloc.s  7
0x2dd5b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2dd60  endfinally
0x2dd61  ret
```
