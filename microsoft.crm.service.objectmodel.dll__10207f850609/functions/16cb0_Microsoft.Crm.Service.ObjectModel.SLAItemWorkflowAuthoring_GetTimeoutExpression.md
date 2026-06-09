# Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::GetTimeoutExpression

- ea: `0x16cb0`
- end: `0x16d35`
- name: `Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::GetTimeoutExpression`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x16c50`
- `0x16dc0`

## string_xrefs

- `0x16d11`: `UIScript_Input_Lookup_BusinessHoursId`

## pseudocode

```c

```

## disassembly

```asm
0x16cb0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object>::.ctor()
0x16cb5  stloc.0
0x16cb6  ldarg.1
0x16cb7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x16cbc  ldarg.0
0x16cbd  ldfld    string Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_applicableFrom
0x16cc2  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x16cc7  stloc.1
0x16cc8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::.ctor()
0x16ccd  stloc.2
0x16cce  ldloc.2
0x16ccf  ldloc.1
0x16cd0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::Add(var<u1>)
0x16cd5  ldarg.1
0x16cd6  ldc.i4.0
0x16cd7  ldloc.2
0x16cd8  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase>::ToArray()
0x16cdd  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x16ce2  stloc.3
0x16ce3  ldloc.0
0x16ce4  ldloc.3
0x16ce5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0x16cea  ldarg.1
0x16ceb  ldarg.0
0x16cec  ldfld    int32 Microsoft.Crm.Service.ObjectModel.SLAItemWorkflowAuthoring::_warnAfter
0x16cf1  box      [mscorlib]System.Int32
0x16cf6  ldc.i4.5
0x16cf7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimitiveExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, object, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x16cfc  stloc.s  4
0x16cfe  ldloc.0
0x16cff  ldloc.s  4
0x16d01  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0x16d06  ldarg.1
0x16d07  ldc.i4.s 0xE
0x16d09  ldc.i4.1
0x16d0a  newarr   [mscorlib]System.Object
0x16d0f  dup
0x16d10  ldc.i4.0
0x16d11  ldstr    aUiscriptInputL// "UIScript_Input_Lookup_BusinessHoursId"
0x16d16  stelem.ref
0x16d17  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x16d1c  stloc.s  5
0x16d1e  ldloc.0
0x16d1f  ldloc.s  5
0x16d21  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0x16d26  ldarg.1
0x16d27  ldc.i4.s 0x15
0x16d29  ldloc.0
0x16d2a  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<object>::ToArray()
0x16d2f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x16d34  ret
```
