# Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked::get_XamlKey

- ea: `0x3f5c0`
- end: `0x3f5ff`
- name: `Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked::get_XamlKey`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x3e780`
- `0x3f320`
- `0x3f560`

## string_xrefs

- `0x3f5c8`: `relatedlinked_`

## pseudocode

```c

```

## disassembly

```asm
0x3f5c0  ldc.i4.6
0x3f5c1  newarr   [mscorlib]System.String
0x3f5c6  dup
0x3f5c7  ldc.i4.0
0x3f5c8  ldstr    aRelatedlinked// "relatedlinked_"
0x3f5cd  stelem.ref
0x3f5ce  dup
0x3f5cf  ldc.i4.1
0x3f5d0  ldarg.0
0x3f5d1  call     instance string Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked::get_RelationshipName()
0x3f5d6  stelem.ref
0x3f5d7  dup
0x3f5d8  ldc.i4.2
0x3f5d9  ldstr    asc_753BE// "#"
0x3f5de  stelem.ref
0x3f5df  dup
0x3f5e0  ldc.i4.3
0x3f5e1  ldarg.0
0x3f5e2  callvirt instance string Microsoft.Crm.Workflow.Expressions.RelatedEntity::get_RelatedAttributeName()
0x3f5e7  stelem.ref
0x3f5e8  dup
0x3f5e9  ldc.i4.4
0x3f5ea  ldstr    asc_753BE// "#"
0x3f5ef  stelem.ref
0x3f5f0  dup
0x3f5f1  ldc.i4.5
0x3f5f2  ldarg.0
0x3f5f3  call     instance string Microsoft.Crm.Workflow.Expressions.EntityBase::get_EntityName()
0x3f5f8  stelem.ref
0x3f5f9  call     string [mscorlib]System.String::Concat(string[])
0x3f5fe  ret
```
