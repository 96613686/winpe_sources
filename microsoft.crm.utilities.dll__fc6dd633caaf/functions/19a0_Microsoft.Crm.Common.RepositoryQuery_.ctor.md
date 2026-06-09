# Microsoft.Crm.Common.RepositoryQuery::.ctor

- ea: `0x19a0`
- end: `0x19c8`
- name: `Microsoft.Crm.Common.RepositoryQuery::.ctor`
- size: `40`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xd60`
- `0xda0`
- `0xe20`
- `0xe30`
- `0x1010`
- `0x1600`

## callees

- `0x19e0`
- `0x1a00`
- `0x1a20`

## pseudocode

```c

```

## disassembly

```asm
0x19a0  ldarg.0
0x19a1  call     instance void [mscorlib]System.Object::.ctor()
0x19a6  ldarg.0
0x19a7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Common.Specification>::.ctor()
0x19ac  call     instance void Microsoft.Crm.Common.RepositoryQuery::set_Specifications(class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Common.Specification> value)
0x19b1  ldarg.0
0x19b2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x19b7  call     instance void Microsoft.Crm.Common.RepositoryQuery::set_PropertiesToReturn(class [mscorlib]System.Collections.Generic.ICollection`1<string> value)
0x19bc  ldarg.0
0x19bd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Common.PropertyOrder>::.ctor()
0x19c2  call     instance void Microsoft.Crm.Common.RepositoryQuery::set_OrderBy(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Common.PropertyOrder> value)
0x19c7  ret
```
