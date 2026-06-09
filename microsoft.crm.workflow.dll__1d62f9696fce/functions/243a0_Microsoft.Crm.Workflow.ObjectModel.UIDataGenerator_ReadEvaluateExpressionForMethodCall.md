# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEvaluateExpressionForMethodCall

- ea: `0x243a0`
- end: `0x24613`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEvaluateExpressionForMethodCall`
- size: `627`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x23fa0`

## callees

- `0x243a0`
- `0x24620`

## pseudocode

```c

```

## disassembly

```asm
0x243a0  ldnull
0x243a1  stloc.0
0x243a2  ldarg.1
0x243a3  ldc.i4.5
0x243a4  sub
0x243a5  switch   loc_243FF, loc_24430, loc_245C2, loc_245C2, loc_24448, loc_24486, loc_24467, loc_244A5, loc_244C4, loc_244E3, loc_24521, loc_245C2, loc_245C2, loc_245C2, loc_24502, loc_24417
0x243ea  ldarg.1
0x243eb  ldc.i4.s 0x28
0x243ed  beq      loc_24540
0x243f2  ldarg.1
0x243f3  ldc.i4.s 0x29
0x243f5  beq      loc_24582
0x243fa  br       loc_245C2
0x243ff  ldarg.0
0x24400  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x24405  ldc.i4.4
0x24406  ldc.i4.0
0x24407  newarr   [mscorlib]System.Object
0x2440c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x24411  stloc.0
0x24412  br       loc_24611
0x24417  ldarg.0
0x24418  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x2441d  ldc.i4.s 0x12
0x2441f  ldc.i4.0
0x24420  newarr   [mscorlib]System.Object
0x24425  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x2442a  stloc.0
0x2442b  br       loc_24611
0x24430  ldarg.0
0x24431  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x24436  ldc.i4.4
0x24437  ldc.i4.0
0x24438  newarr   [mscorlib]System.Object
0x2443d  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x24442  stloc.0
0x24443  br       loc_24611
0x24448  ldarg.0
0x24449  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x2444e  ldc.i4.s 9
0x24450  ldc.i4.1
0x24451  newarr   [mscorlib]System.Object
0x24456  dup
0x24457  ldc.i4.0
0x24458  ldarg.2
0x24459  ldc.i4.0
0x2445a  ldelem.ref
0x2445b  stelem.ref
0x2445c  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x24461  stloc.0
0x24462  br       loc_24611
0x24467  ldarg.0
0x24468  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x2446d  ldc.i4.s 0xB
0x2446f  ldc.i4.1
0x24470  newarr   [mscorlib]System.Object
0x24475  dup
0x24476  ldc.i4.0
0x24477  ldarg.2
0x24478  ldc.i4.0
0x24479  ldelem.ref
0x2447a  stelem.ref
0x2447b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x24480  stloc.0
0x24481  br       loc_24611
0x24486  ldarg.0
0x24487  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x2448c  ldc.i4.s 0xA
0x2448e  ldc.i4.1
0x2448f  newarr   [mscorlib]System.Object
0x24494  dup
0x24495  ldc.i4.0
0x24496  ldarg.2
0x24497  ldc.i4.0
0x24498  ldelem.ref
0x24499  stelem.ref
0x2449a  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x2449f  stloc.0
0x244a0  br       loc_24611
0x244a5  ldarg.0
0x244a6  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x244ab  ldc.i4.s 0xC
0x244ad  ldc.i4.1
0x244ae  newarr   [mscorlib]System.Object
0x244b3  dup
0x244b4  ldc.i4.0
0x244b5  ldarg.2
0x244b6  ldc.i4.0
0x244b7  ldelem.ref
0x244b8  stelem.ref
0x244b9  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x244be  stloc.0
0x244bf  br       loc_24611
0x244c4  ldarg.0
0x244c5  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x244ca  ldc.i4.s 0xD
0x244cc  ldc.i4.1
0x244cd  newarr   [mscorlib]System.Object
0x244d2  dup
0x244d3  ldc.i4.0
0x244d4  ldarg.2
0x244d5  ldc.i4.0
0x244d6  ldelem.ref
0x244d7  stelem.ref
0x244d8  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x244dd  stloc.0
0x244de  br       loc_24611
0x244e3  ldarg.0
0x244e4  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x244e9  ldc.i4.s 0xE
0x244eb  ldc.i4.1
0x244ec  newarr   [mscorlib]System.Object
0x244f1  dup
0x244f2  ldc.i4.0
0x244f3  ldarg.2
0x244f4  ldc.i4.0
0x244f5  ldelem.ref
0x244f6  stelem.ref
0x244f7  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x244fc  stloc.0
0x244fd  br       loc_24611
0x24502  ldarg.0
0x24503  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x24508  ldc.i4.s 0x11
0x2450a  ldc.i4.1
0x2450b  newarr   [mscorlib]System.Object
0x24510  dup
0x24511  ldc.i4.0
0x24512  ldarg.2
0x24513  ldc.i4.0
0x24514  ldelem.ref
0x24515  stelem.ref
0x24516  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x2451b  stloc.0
0x2451c  br       loc_24611
0x24521  ldarg.0
0x24522  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x24527  ldc.i4.s 0xF
0x24529  ldc.i4.1
0x2452a  newarr   [mscorlib]System.Object
0x2452f  dup
0x24530  ldc.i4.0
0x24531  ldarg.2
0x24532  ldc.i4.0
0x24533  ldelem.ref
0x24534  stelem.ref
0x24535  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x2453a  stloc.0
0x2453b  br       loc_24611
0x24540  ldarg.2
0x24541  ldlen
0x24542  conv.i4
0x24543  newarr   [mscorlib]System.Object
0x24548  stloc.1
0x24549  ldc.i4.0
0x2454a  stloc.s  5
0x2454c  br.s     loc_24567
0x2454e  ldloc.1
0x2454f  ldloc.s  5
0x24551  ldarg.0
0x24552  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x24557  ldarg.2
0x24558  ldloc.s  5
0x2455a  ldelem.ref
0x2455b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x24560  stelem.ref
0x24561  ldloc.s  5
0x24563  ldc.i4.1
0x24564  add
0x24565  stloc.s  5
0x24567  ldloc.s  5
0x24569  ldarg.2
0x2456a  ldlen
0x2456b  conv.i4
0x2456c  blt.s    loc_2454E
0x2456e  ldarg.0
0x2456f  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x24574  ldc.i4.s 0x16
0x24576  ldloc.1
0x24577  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x2457c  stloc.0
0x2457d  br       loc_24611
0x24582  ldc.i4.2
0x24583  newarr   [mscorlib]System.Object
0x24588  dup
0x24589  ldc.i4.0
0x2458a  ldarg.2
0x2458b  ldc.i4.0
0x2458c  ldelem.ref
0x2458d  stelem.ref
0x2458e  dup
0x2458f  ldc.i4.1
0x24590  ldarg.0
0x24591  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x24596  ldarg.2
0x24597  ldc.i4.1
0x24598  ldelem.ref
0x24599  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2459e  stelem.ref
0x2459f  stloc.2
0x245a0  ldarg.0
0x245a1  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x245a6  ldc.i4.s 0x17
0x245a8  ldloc.2
0x245a9  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x245ae  stloc.0
0x245af  ldarg.2
0x245b0  ldc.i4.0
0x245b1  ldelem.ref
0x245b2  stloc.3
0x245b3  ldloc.0
0x245b4  ldarg.0
0x245b5  ldloc.3
0x245b6  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::GetBpfAttributeType(string bpfAttributeType)
0x245bb  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase::set_Type(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x245c0  br.s     loc_24611
0x245c2  ldarg.2
0x245c3  ldlen
0x245c4  conv.i4
0x245c5  ldc.i4.1
0x245c6  add
0x245c7  newarr   [mscorlib]System.Object
0x245cc  stloc.s  4
0x245ce  ldloc.s  4
0x245d0  ldc.i4.0
0x245d1  ldarg.1
0x245d2  box      [Microsoft.Crm]Microsoft.Crm.Workflow.Activities.ExpressionOperator
0x245d7  stelem.ref
0x245d8  ldc.i4.1
0x245d9  stloc.s  6
0x245db  br.s     loc_245F9
0x245dd  ldloc.s  4
0x245df  ldloc.s  6
0x245e1  ldarg.0
0x245e2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x245e7  ldarg.2
0x245e8  ldloc.s  6
0x245ea  ldc.i4.1
0x245eb  sub
0x245ec  ldelem.ref
0x245ed  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x245f2  stelem.ref
0x245f3  ldloc.s  6
0x245f5  ldc.i4.1
0x245f6  add
0x245f7  stloc.s  6
0x245f9  ldloc.s  6
0x245fb  ldarg.2
0x245fc  ldlen
0x245fd  conv.i4
0x245fe  ldc.i4.1
0x245ff  add
0x24600  blt.s    loc_245DD
0x24602  ldarg.0
0x24603  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x24608  ldc.i4.3
0x24609  ldloc.s  4
0x2460b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x24610  stloc.0
0x24611  ldloc.0
0x24612  ret
```
