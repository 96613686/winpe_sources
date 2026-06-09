# Microsoft.Crm.ApplicationConfig::SchedulingCacheTimeout

- ea: `0x18c00`
- end: `0x18c2d`
- name: `Microsoft.Crm.ApplicationConfig::SchedulingCacheTimeout`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18fb0`

## string_xrefs

- `0x18c00`: `SchedulingCacheTimeout`

## pseudocode

```c

```

## disassembly

```asm
0x18c00  ldstr    aSchedulingcach// "SchedulingCacheTimeout"
0x18c05  ldc.r8   1.0
0x18c0e  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromHours(float64)
0x18c13  stloc.0
0x18c14  ldloca.s 0
0x18c16  call     instance float64 [mscorlib]System.TimeSpan::get_TotalSeconds()
0x18c1b  conv.i4
0x18c1c  box      [mscorlib]System.Int32
0x18c21  ldarg.0
0x18c22  call     object Microsoft.Crm.ApplicationConfig::Retrieve(string propertyName, object defaultValue, valuetype [mscorlib]System.Guid organizationId)
0x18c27  unbox.any [mscorlib]System.Int32
0x18c2c  ret
```
