# Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum

- ea: `0x340`
- end: `0x35f`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xaac0`

## callees

- `0x200`
- `0x340`

## pseudocode

```c

```

## disassembly

```asm
0x340  ldarg.0
0x341  ldarg.1
0x342  ldnull
0x343  call     instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x348  stloc.0
0x349  ldloc.0
0x34a  brfalse.s loc_355
0x34c  ldloc.0
0x34d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x352  ldc.i4.0
0x353  bgt.s    loc_357
0x355  ldarg.3
0x356  ret
0x357  ldarg.2
0x358  ldloc.0
0x359  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x35e  ret
```
