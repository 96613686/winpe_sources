# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntitySpecification

- ea: `0x22c00`
- end: `0x22c4f`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntitySpecification`
- size: `79`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1fd50`
- `0x1fe30`
- `0x1ff20`
- `0x209c0`

## callees

- `0x22c00`
- `0x22c50`
- `0x22c90`

## pseudocode

```c

```

## disassembly

```asm
0x22c00  ldarg.3
0x22c01  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::.ctor(string)
0x22c06  stloc.0
0x22c07  ldc.i4.0
0x22c08  stloc.1
0x22c09  br.s     loc_22C39
0x22c0b  ldarg.0
0x22c0c  ldarg.1
0x22c0d  ldloc.1
0x22c0e  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x22c13  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x22c18  call     instance bool Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::IsAssignType(class [mscorlib]System.Type type)
0x22c1d  brtrue.s loc_22C35
0x22c1f  ldarg.0
0x22c20  ldarg.1
0x22c21  ldloca.s 1
0x22c23  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadPropertySpecification(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity> activities, int32& activityIndex)
0x22c28  stloc.2
0x22c29  ldloc.0
0x22c2a  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification> [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::get_Properties()
0x22c2f  ldloc.2
0x22c30  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PropertySpecification>::Add(var<u1>)
0x22c35  ldloc.1
0x22c36  ldc.i4.1
0x22c37  add
0x22c38  stloc.1
0x22c39  ldarg.1
0x22c3a  ldloc.1
0x22c3b  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Activity>::get_Item(!!T0)
0x22c40  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x22c45  ldarg.2
0x22c46  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x22c4b  brtrue.s loc_22C0B
0x22c4d  ldloc.0
0x22c4e  ret
```
