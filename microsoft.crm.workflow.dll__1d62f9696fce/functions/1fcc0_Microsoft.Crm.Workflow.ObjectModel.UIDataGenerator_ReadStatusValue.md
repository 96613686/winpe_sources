# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStatusValue

- ea: `0x1fcc0`
- end: `0x1fd09`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadStatusValue`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1fd10`
- `0x228e0`

## string_xrefs

- `0x1fcc0`: `New Microsoft.Xrm.Sdk.InvalidPluginExecutionException(Microsoft.Xrm.Sdk.OperationStatus.`

## pseudocode

```c

```

## disassembly

```asm
0x1fcc0  ldstr    aNewMicrosoftXr// "New Microsoft.Xrm.Sdk.InvalidPluginExec"...
0x1fcc5  call     instance int32 [mscorlib]System.String::get_Length()
0x1fcca  stloc.0
0x1fccb  ldarg.0
0x1fccc  callvirt instance class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Exception> [System.Activities]System.Activities.Statements.TerminateWorkflow::get_Exception()
0x1fcd1  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<class [mscorlib]System.Exception>::get_Expression()
0x1fcd6  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [mscorlib]System.Exception>
0x1fcdb  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<class [mscorlib]System.Exception>::get_ExpressionText()
0x1fce0  stloc.1
0x1fce1  ldloc.1
0x1fce2  ldloc.0
0x1fce3  ldloc.1
0x1fce4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1fce9  ldloc.0
0x1fcea  sub
0x1fceb  ldc.i4.1
0x1fcec  sub
0x1fced  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1fcf2  stloc.2
0x1fcf3  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.Activities.WorkflowCompletionStatus
0x1fcf8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1fcfd  ldloc.2
0x1fcfe  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x1fd03  unbox.any [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.Activities.WorkflowCompletionStatus
0x1fd08  ret
```
