# Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid

- ea: `0x310`
- end: `0x32e`
- name: `Microsoft.Crm.Application.WebServices.ParameterBag::GetGuid`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xbe0`
- `0x1ed0`
- `0x9a10`
- `0x9bd0`
- `0xa0c0`

## callees

- `0x200`
- `0x310`

## pseudocode

```c

```

## disassembly

```asm
0x310  ldarg.0
0x311  ldarg.1
0x312  ldnull
0x313  call     instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x318  stloc.0
0x319  ldloc.0
0x31a  brfalse.s loc_325
0x31c  ldloc.0
0x31d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x322  ldc.i4.0
0x323  bgt.s    loc_327
0x325  ldarg.2
0x326  ret
0x327  ldloc.0
0x328  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x32d  ret
```
