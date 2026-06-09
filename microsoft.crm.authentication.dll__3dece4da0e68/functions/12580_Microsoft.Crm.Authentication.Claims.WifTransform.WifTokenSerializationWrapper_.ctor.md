# Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::.ctor

- ea: `0x12580`
- end: `0x1259d`
- name: `Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::.ctor`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xada0`

## callees

- `0x12580`
- `0x127a0`

## string_xrefs

- `0x12590`: `The provided wifTokenData does not look like a valid WIF Token`

## pseudocode

```c

```

## disassembly

```asm
0x12580  ldarg.0
0x12581  call     instance void [mscorlib]System.Object::.ctor()
0x12586  ldarg.0
0x12587  ldarg.1
0x12588  call     instance void Microsoft.Crm.Authentication.Claims.WifTransform.WifTokenSerializationWrapper::ReadWifTokenData(unsigned int8[] tokenData)
0x1258d  leave.s  loc_1259C
0x1258f  stloc.0
0x12590  ldstr    aTheProvidedWif// "The provided wifTokenData does not look"...
0x12595  ldloc.0
0x12596  newobj   instance void [mscorlib]System.InvalidCastException::.ctor(string, class [mscorlib]System.Exception)
0x1259b  throw
0x1259c  ret
```
