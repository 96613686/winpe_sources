# Microsoft.Crm.Common.Repository::BuildCacheKey

- ea: `0x1600`
- end: `0x1631`
- name: `Microsoft.Crm.Common.Repository::BuildCacheKey`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x12c0`
- `0x1600`
- `0x19a0`

## pseudocode

```c

```

## disassembly

```asm
0x1600  ldarg.0
0x1601  brtrue.s loc_160E
0x1603  ldstr    aSpecifications// "specificationsExpression"
0x1608  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x160d  throw
0x160e  newobj   instance void Microsoft.Crm.Common.RepositoryQuery::.ctor()
0x1613  stloc.0
0x1614  ldarg.0
0x1615  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.LambdaExpression::get_Body()
0x161a  ldloc.0
0x161b  ldtoken  mvar<u1>
0x1620  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1625  call     void Microsoft.Crm.Common.Repository::ParseExpression(class [System.Core]System.Linq.Expressions.Expression expression, class Microsoft.Crm.Common.RepositoryQuery query, class [mscorlib]System.Type expectedType)
0x162a  ldloc.0
0x162b  call     T0x2B00000B
0x1630  ret
```
