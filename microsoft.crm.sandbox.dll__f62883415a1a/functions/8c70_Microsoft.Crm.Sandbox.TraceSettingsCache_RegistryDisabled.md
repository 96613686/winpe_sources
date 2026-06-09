# Microsoft.Crm.Sandbox.TraceSettingsCache::RegistryDisabled

- ea: `0x8c70`
- end: `0x8c9e`
- name: `Microsoft.Crm.Sandbox.TraceSettingsCache::RegistryDisabled`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8c50`

## callees

- `0x8c70`

## pseudocode

```c

```

## disassembly

```asm
0x8c70  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x8c75  callvirt instance bool [mscorlib]System.AppDomain::get_IsFullyTrusted()
0x8c7a  brfalse.s loc_8C9C
0x8c7c  ldstr    aTraceenabled// "TraceEnabled"
0x8c81  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x8c86  stloc.0
0x8c87  ldloc.0
0x8c88  brfalse.s loc_8C9C
0x8c8a  ldloc.0
0x8c8b  isinst   [mscorlib]System.Int32
0x8c90  brfalse.s loc_8C9C
0x8c92  ldloc.0
0x8c93  unbox.any [mscorlib]System.Int32
0x8c98  brtrue.s loc_8C9C
0x8c9a  ldc.i4.1
0x8c9b  ret
0x8c9c  ldc.i4.0
0x8c9d  ret
```
