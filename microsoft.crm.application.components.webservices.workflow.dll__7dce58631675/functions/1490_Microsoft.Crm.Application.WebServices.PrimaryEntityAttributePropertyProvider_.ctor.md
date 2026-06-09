# Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::.ctor

- ea: `0x1490`
- end: `0x14bb`
- name: `Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::.ctor`
- size: `43`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xbf0`
- `0xcd0`
- `0xcf0`
- `0xd10`
- `0xda0`
- `0xf20`
- `0xfe0`
- `0x1000`
- `0x1020`
- `0x1110`
- `0x1240`

## callees

- `0x1420`
- `0x1480`

## pseudocode

```c

```

## disassembly

```asm
0x1490  ldarg.0
0x1491  call     instance void [mscorlib]System.Object::.ctor()
0x1496  ldc.i4.1
0x1497  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression
0x149c  dup
0x149d  ldc.i4.0
0x149e  ldarg.3
0x149f  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x14a4  ldarg.2
0x14a5  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase, string)
0x14aa  stelem.ref
0x14ab  stloc.0
0x14ac  ldarg.0
0x14ad  ldarg.1
0x14ae  ldloc.0
0x14af  ldarg.3
0x14b0  newobj   instance void Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::.ctor(string targetAttributeName, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression[] sourceAttributeExpressions, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x14b5  call     instance void Microsoft.Crm.Application.WebServices.PrimaryEntityAttributePropertyProvider::set_EntityAttributePropertyProvider(class Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider value)
0x14ba  ret
```
