# Microsoft.Xrm.Async.Bridges.WebApp.Models.ClaimInfo::.ctor

- ea: `0x2b0`
- end: `0x2cf`
- name: `Microsoft.Xrm.Async.Bridges.WebApp.Models.ClaimInfo::.ctor`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4a0`

## pseudocode

```c

```

## disassembly

```asm
0x2b0  ldarg.0
0x2b1  call     instance void [mscorlib]System.Object::.ctor()
0x2b6  ldarg.0
0x2b7  ldarg.1
0x2b8  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Type()
0x2bd  stfld    string Microsoft.Xrm.Async.Bridges.WebApp.Models.ClaimInfo::<Name>k__BackingField
0x2c2  ldarg.0
0x2c3  ldarg.1
0x2c4  callvirt instance string [mscorlib]System.Security.Claims.Claim::get_Value()
0x2c9  stfld    string Microsoft.Xrm.Async.Bridges.WebApp.Models.ClaimInfo::<Value>k__BackingField
0x2ce  ret
```
