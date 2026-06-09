# Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateSqlWithPagingConditionPickList

- ea: `0x1c520`
- end: `0x1c5b8`
- name: `Microsoft.Crm.Asynchronous.ImportOperationTransform::UpdateSqlWithPagingConditionPickList`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c180`

## pseudocode

```c

```

## disassembly

```asm
0x1c520  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1c525  dup
0x1c526  ldarg.1
0x1c527  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c52c  pop
0x1c52d  dup
0x1c52e  ldstr    aFrom_1// " from "
0x1c533  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c538  pop
0x1c539  dup
0x1c53a  ldarg.2
0x1c53b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c540  pop
0x1c541  dup
0x1c542  ldstr    aWhere// " where (("
0x1c547  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c54c  pop
0x1c54d  dup
0x1c54e  ldarg.2
0x1c54f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c554  pop
0x1c555  dup
0x1c556  ldstr    aSnBetween// ".SN between "
0x1c55b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c560  pop
0x1c561  dup
0x1c562  ldarg.3
0x1c563  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int64)
0x1c568  pop
0x1c569  dup
0x1c56a  ldstr    aAnd// " and "
0x1c56f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c574  pop
0x1c575  dup
0x1c576  ldarg.s  4
0x1c578  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int64)
0x1c57d  pop
0x1c57e  dup
0x1c57f  ldstr    aAnd_0// ") AND "
0x1c584  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c589  pop
0x1c58a  dup
0x1c58b  ldarg.2
0x1c58c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c591  pop
0x1c592  dup
0x1c593  ldstr    aIstransformed_0// ".IsTransformed <= "
0x1c598  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c59d  pop
0x1c59e  dup
0x1c59f  ldc.i4.8
0x1c5a0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(int32)
0x1c5a5  pop
0x1c5a6  dup
0x1c5a7  ldstr    asc_275CE// ")"
0x1c5ac  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1c5b1  pop
0x1c5b2  callvirt instance string [mscorlib]System.Object::ToString()
0x1c5b7  ret
```
