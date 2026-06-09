# Microsoft.Crm.Common.Repository::VerifyPropertySelectorMemberExpression

- ea: `0x1150`
- end: `0x11ae`
- name: `Microsoft.Crm.Common.Repository::VerifyPropertySelectorMemberExpression`
- size: `94`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xf40`
- `0x10a0`

## callees

- `0x1150`

## pseudocode

```c

```

## disassembly

```asm
0x1150  ldarg.2
0x1151  brtrue.s loc_115E
0x1153  ldstr    aExpressionWasN// "Expression was not a MemberExpression"
0x1158  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x115d  throw
0x115e  ldarg.2
0x115f  callvirt instance class [mscorlib]System.Reflection.MemberInfo [System.Core]System.Linq.Expressions.MemberExpression::get_Member()
0x1164  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MemberInfo::get_DeclaringType()
0x1169  ldarg.0
0x116a  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x116f  brfalse.s loc_117C
0x1171  ldstr    aExpressionDidN// "Expression did not use the expected typ"...
0x1176  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x117b  throw
0x117c  ldarg.2
0x117d  callvirt instance class [System.Core]System.Linq.Expressions.Expression [System.Core]System.Linq.Expressions.MemberExpression::get_Expression()
0x1182  isinst   [System.Core]System.Linq.Expressions.ParameterExpression
0x1187  dup
0x1188  brtrue.s loc_1195
0x118a  ldstr    aExpressionWasN_1// "Expression was not using an input param"...
0x118f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1194  throw
0x1195  callvirt instance string [System.Core]System.Linq.Expressions.ParameterExpression::get_Name()
0x119a  ldarg.1
0x119b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x11a0  brfalse.s loc_11AD
0x11a2  ldstr    aExpressionWasN_2// "Expression was not using the correct in"...
0x11a7  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x11ac  throw
0x11ad  ret
```
