# Microsoft.Crm.Common.Repository::IsNullableEnum

- ea: `0x1570`
- end: `0x15b0`
- name: `Microsoft.Crm.Common.Repository::IsNullableEnum`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14d0`

## callees

- `0x1570`

## pseudocode

```c

```

## disassembly

```asm
0x1570  ldarg.0
0x1571  callvirt instance bool [mscorlib]System.Type::get_IsGenericType()
0x1576  brfalse.s loc_158F
0x1578  ldarg.0
0x1579  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetGenericTypeDefinition()
0x157e  ldtoken  [mscorlib]System.Nullable`1
0x1583  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1588  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x158d  br.s     loc_1590
0x158f  ldc.i4.0
0x1590  brfalse.s loc_15AE
0x1592  ldarg.0
0x1593  callvirt instance class [mscorlib]System.Type[] [mscorlib]System.Type::GetGenericArguments()
0x1598  stloc.0
0x1599  ldloc.0
0x159a  brfalse.s loc_15AE
0x159c  ldloc.0
0x159d  ldlen
0x159e  conv.i4
0x159f  ldc.i4.1
0x15a0  bne.un.s loc_15AE
0x15a2  ldloc.0
0x15a3  ldc.i4.0
0x15a4  ldelem.ref
0x15a5  callvirt instance bool [mscorlib]System.Type::get_IsEnum()
0x15aa  brfalse.s loc_15AE
0x15ac  ldc.i4.1
0x15ad  ret
0x15ae  ldc.i4.0
0x15af  ret
```
