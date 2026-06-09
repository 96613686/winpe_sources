# Microsoft.Crm.Application.WebServices.ParameterBag::GetBool

- ea: `0x290`
- end: `0x2ae`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::GetBool`
- size: `30`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x390`
- `0x20e0`
- `0x2cd0`
- `0x2e00`
- `0x2e20`
- `0x2e40`
- `0x2e80`
- `0x3c90`
- `0x3da0`
- `0x3dc0`
- `0x3de0`
- `0x3f20`
- `0xa0c0`

## callees

- `0x200`
- `0x290`

## pseudocode

```c

```

## disassembly

```asm
0x290  ldarg.0
0x291  ldarg.1
0x292  ldnull
0x293  call     instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x298  stloc.0
0x299  ldloc.0
0x29a  brfalse.s loc_2A5
0x29c  ldloc.0
0x29d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2a2  ldc.i4.0
0x2a3  bgt.s    loc_2A7
0x2a5  ldarg.2
0x2a6  ret
0x2a7  ldloc.0
0x2a8  call     bool [mscorlib]System.Boolean::Parse(string)
0x2ad  ret
```
