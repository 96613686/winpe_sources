# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetDataSourceFromParameterBag

- ea: `0x1b90`
- end: `0x1bcb`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetDataSourceFromParameterBag`
- size: `59`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xaf0`
- `0xbe0`
- `0x1000`
- `0x1400`
- `0x1580`
- `0x1650`
- `0x17d0`

## callees

- `0x220`
- `0x1b90`

## pseudocode

```c

```

## disassembly

```asm
0x1b90  ldarg.0
0x1b91  ldstr    aSourcetype// "sourcetype"
0x1b96  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x1b9b  stloc.0
0x1b9c  ldloc.0
0x1b9d  ldstr    aCalculated// "Calculated"
0x1ba2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ba7  brtrue.s loc_1BC5
0x1ba9  ldloc.0
0x1baa  ldstr    aRollup// "Rollup"
0x1baf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bb4  brtrue.s loc_1BC7
0x1bb6  ldloc.0
0x1bb7  ldstr    aPersistent// "Persistent"
0x1bbc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bc1  brtrue.s loc_1BC9
0x1bc3  br.s     loc_1BC9
0x1bc5  ldc.i4.1
0x1bc6  ret
0x1bc7  ldc.i4.2
0x1bc8  ret
0x1bc9  ldc.i4.0
0x1bca  ret
```
