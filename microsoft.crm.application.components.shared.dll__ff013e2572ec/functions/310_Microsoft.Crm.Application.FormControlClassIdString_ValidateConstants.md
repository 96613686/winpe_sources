# Microsoft.Crm.Application.FormControlClassIdString::ValidateConstants

- ea: `0x310`
- end: `0x35b`
- name: `Microsoft.Crm.Application.FormControlClassIdString::ValidateConstants`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x310`

## pseudocode

```c

```

## disassembly

```asm
0x310  ldtoken  Microsoft.Crm.Application.FormControlClassIdString
0x315  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x31a  ldc.i4.s 0x18
0x31c  callvirt instance class [mscorlib]System.Reflection.FieldInfo[] [mscorlib]System.Type::GetFields(valuetype [mscorlib]System.Reflection.BindingFlags)
0x321  stloc.0
0x322  ldc.i4.0
0x323  stloc.1
0x324  br.s     loc_354
0x326  ldloc.0
0x327  ldloc.1
0x328  ldelem.ref
0x329  stloc.2
0x32a  ldloc.2
0x32b  callvirt instance bool [mscorlib]System.Reflection.FieldInfo::get_IsLiteral()
0x330  brfalse.s loc_350
0x332  ldloc.2
0x333  ldnull
0x334  callvirt instance object [mscorlib]System.Reflection.FieldInfo::GetValue(object)
0x339  castclass [mscorlib]System.String
0x33e  dup
0x33f  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x344  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x349  brfalse.s loc_350
0x34b  call     void [mscorlib]System.Diagnostics.Debugger::Break()
0x350  ldloc.1
0x351  ldc.i4.1
0x352  add
0x353  stloc.1
0x354  ldloc.1
0x355  ldloc.0
0x356  ldlen
0x357  conv.i4
0x358  blt.s    loc_326
0x35a  ret
```
