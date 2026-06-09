# Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::.ctor

- ea: `0x1420`
- end: `0x143c`
- name: `Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::.ctor`
- size: `28`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xde0`
- `0xf40`
- `0x1040`
- `0x1080`
- `0x1130`
- `0x1170`
- `0x1260`
- `0x12a0`
- `0x1300`
- `0x1490`

## callees

- `0x13d0`
- `0x13f0`
- `0x1410`

## pseudocode

```c

```

## disassembly

```asm
0x1420  ldarg.0
0x1421  call     instance void [mscorlib]System.Object::.ctor()
0x1426  ldarg.0
0x1427  ldarg.1
0x1428  call     instance void Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::set_TargetAttributeName(string value)
0x142d  ldarg.0
0x142e  ldarg.2
0x142f  call     instance void Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::set_SourceAttributeExpressions(class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityAttributeExpression[] value)
0x1434  ldarg.0
0x1435  ldarg.3
0x1436  call     instance void Microsoft.Crm.Application.WebServices.EntityAttributePropertyProvider::set_Workflow(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep value)
0x143b  ret
```
