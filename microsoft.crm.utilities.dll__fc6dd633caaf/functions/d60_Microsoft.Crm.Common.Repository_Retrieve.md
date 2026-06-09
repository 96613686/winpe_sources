# Microsoft.Crm.Common.Repository::Retrieve

- ea: `0xd60`
- end: `0xd93`
- name: `Microsoft.Crm.Common.Repository::Retrieve`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xd60`
- `0x12c0`
- `0x19a0`

## pseudocode

```c

```

## disassembly

```asm
0xd60  ldarg.1
0xd61  brtrue.s loc_D6E
0xd63  ldstr    aSpecifications// "specificationsExpression"
0xd68  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd6d  throw
0xd6e  newobj   instance void Microsoft.Crm.Common.RepositoryQuery::.ctor()
0xd73  stloc.0
0xd74  ldarg.1
0xd75  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.LambdaExpression::get_Body()
0xd7a  ldloc.0
0xd7b  ldtoken  mvar<u1>
0xd80  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xd85  call     void Microsoft.Crm.Common.Repository::ParseExpression(class [System.Core]System.Linq.Expressions.Expression expression, class Microsoft.Crm.Common.RepositoryQuery query, class [mscorlib]System.Type expectedType)
0xd8a  ldarg.0
0xd8b  ldloc.0
0xd8c  ldc.i4.1
0xd8d  call     T0x2B000003
0xd92  ret
```
