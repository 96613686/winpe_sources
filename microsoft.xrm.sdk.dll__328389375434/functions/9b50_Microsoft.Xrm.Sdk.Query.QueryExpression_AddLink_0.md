# Microsoft.Xrm.Sdk.Query.QueryExpression::AddLink_0

- ea: `0x9b50`
- end: `0x9b6f`
- name: `Microsoft.Xrm.Sdk.Query.QueryExpression::AddLink_0`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x9b40`
- `0xc3b0`

## callees

- `0x92a0`
- `0x9a20`
- `0x9aa0`

## pseudocode

```c

```

## disassembly

```asm
0x9b50  ldarg.0
0x9b51  call     instance string Microsoft.Xrm.Sdk.Query.QueryExpression::get_EntityName()
0x9b56  ldarg.1
0x9b57  ldarg.2
0x9b58  ldarg.3
0x9b59  ldarg.s  4
0x9b5b  newobj   instance void Microsoft.Xrm.Sdk.Query.LinkEntity::.ctor(string linkFromEntityName, string linkToEntityName, string linkFromAttributeName, string linkToAttributeName, valuetype Microsoft.Xrm.Sdk.Query.JoinOperator joinOperator)
0x9b60  stloc.0
0x9b61  ldarg.0
0x9b62  call     instance class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.LinkEntity> Microsoft.Xrm.Sdk.Query.QueryExpression::get_LinkEntities()
0x9b67  ldloc.0
0x9b68  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Xrm.Sdk.Query.LinkEntity>::Add(var<u1>)
0x9b6d  ldloc.0
0x9b6e  ret
```
