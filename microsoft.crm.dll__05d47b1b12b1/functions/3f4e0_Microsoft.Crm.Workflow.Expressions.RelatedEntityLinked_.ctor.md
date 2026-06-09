# Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked::.ctor

- ea: `0x3f4e0`
- end: `0x3f53a`
- name: `Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked::.ctor`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2cb30`

## callees

- `0x3e7e0`
- `0x3f2e0`

## string_xrefs

- `0x3f52f`: `RelatedEntityLinked:#Microsoft.Crm.Workflow.Expressions`
- `0x3f4f2`: `relatedlinked_`

## pseudocode

```c

```

## disassembly

```asm
0x3f4e0  ldarg.0
0x3f4e1  ldarg.1
0x3f4e2  ldarg.2
0x3f4e3  ldarg.3
0x3f4e4  call     instance void Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflow, string relatedAttributeName, string relatedEntity)
0x3f4e9  ldarg.0
0x3f4ea  ldc.i4.6
0x3f4eb  newarr   [mscorlib]System.String
0x3f4f0  dup
0x3f4f1  ldc.i4.0
0x3f4f2  ldstr    aRelatedlinked// "relatedlinked_"
0x3f4f7  stelem.ref
0x3f4f8  dup
0x3f4f9  ldc.i4.1
0x3f4fa  ldarg.s  4
0x3f4fc  stelem.ref
0x3f4fd  dup
0x3f4fe  ldc.i4.2
0x3f4ff  ldstr    asc_753BA// "_"
0x3f504  stelem.ref
0x3f505  dup
0x3f506  ldc.i4.3
0x3f507  ldarg.2
0x3f508  stelem.ref
0x3f509  dup
0x3f50a  ldc.i4.4
0x3f50b  ldstr    asc_753BA// "_"
0x3f510  stelem.ref
0x3f511  dup
0x3f512  ldc.i4.5
0x3f513  ldarg.3
0x3f514  stelem.ref
0x3f515  call     string [mscorlib]System.String::Concat(string[])
0x3f51a  call     instance void Microsoft.Crm.Workflow.Expressions.EntityBase::set_ParameterName(string value)
0x3f51f  ldarg.0
0x3f520  ldarg.2
0x3f521  stfld    string Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked::relatedAttributeName
0x3f526  ldarg.0
0x3f527  ldarg.s  4
0x3f529  stfld    string Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked::relationshipName
0x3f52e  ldarg.0
0x3f52f  ldstr    aRelatedentityl// "RelatedEntityLinked:#Microsoft.Crm.Work"...
0x3f534  stfld    string Microsoft.Crm.Workflow.Expressions.EntityBase::__class
0x3f539  ret
```
