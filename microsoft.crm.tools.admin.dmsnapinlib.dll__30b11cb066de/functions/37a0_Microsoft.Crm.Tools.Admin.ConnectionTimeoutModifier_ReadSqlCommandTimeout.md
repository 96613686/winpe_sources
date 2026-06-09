# Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::ReadSqlCommandTimeout

- ea: `0x37a0`
- end: `0x37c9`
- name: `Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::ReadSqlCommandTimeout`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x36d0`

## callees

- `0x37a0`

## string_xrefs

- `0x37a6`: `SqlCommandTimeout`

## pseudocode

```c

```

## disassembly

```asm
0x37a0  ldarg.0
0x37a1  brtrue.s loc_37A5
0x37a3  ldc.i4.m1
0x37a4  ret
0x37a5  ldarg.0
0x37a6  ldstr    aSqlcommandtime// "SqlCommandTimeout"
0x37ab  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x37b0  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0x37b5  stloc.0
0x37b6  ldloca.s 0
0x37b8  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x37bd  brfalse.s loc_37C7
0x37bf  ldloca.s 0
0x37c1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x37c6  ret
0x37c7  ldc.i4.m1
0x37c8  ret
```
