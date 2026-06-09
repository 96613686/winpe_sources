# Microsoft.Crm.Common.Repository::RetrieveSkipCache

- ea: `0xda0`
- end: `0xdd3`
- name: `Microsoft.Crm.Common.Repository::RetrieveSkipCache`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xda0`
- `0x12c0`
- `0x19a0`

## pseudocode

```c

```

## disassembly

```asm
0xda0  ldarg.1
0xda1  brtrue.s loc_DAE
0xda3  ldstr    aSpecifications// "specificationsExpression"
0xda8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xdad  throw
0xdae  newobj   instance void Microsoft.Crm.Common.RepositoryQuery::.ctor()
0xdb3  stloc.0
0xdb4  ldarg.1
0xdb5  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.LambdaExpression::get_Body()
0xdba  ldloc.0
0xdbb  ldtoken  mvar<u1>
0xdc0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xdc5  call     void Microsoft.Crm.Common.Repository::ParseExpression(class [System.Core]System.Linq.Expressions.Expression expression, class Microsoft.Crm.Common.RepositoryQuery query, class [mscorlib]System.Type expectedType)
0xdca  ldarg.0
0xdcb  ldloc.0
0xdcc  ldc.i4.0
0xdcd  call     T0x2B000003
0xdd2  ret
```
