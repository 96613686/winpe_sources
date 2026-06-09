# Microsoft.Crm.Sandbox.TraceSettingsCache::GetHighestTraceLevel

- ea: `0x8c50`
- end: `0x8c70`
- name: `Microsoft.Crm.Sandbox.TraceSettingsCache::GetHighestTraceLevel`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1740`
- `0x8c40`

## callees

- `0x8bc0`
- `0x8c50`
- `0x8c70`
- `0x8d00`

## pseudocode

```c

```

## disassembly

```asm
0x8c50  ldarg.0
0x8c51  call     instance bool Microsoft.Crm.Sandbox.TraceSettingsCache::RegistryDisabled()
0x8c56  brtrue.s loc_8C60
0x8c58  ldarg.0
0x8c59  ldfld    bool Microsoft.Crm.Sandbox.TraceSettingsCache::_traceDisabled
0x8c5e  brfalse.s loc_8C62
0x8c60  ldc.i4.0
0x8c61  ret
0x8c62  ldarg.0
0x8c63  ldarg.1
0x8c64  ldarg.0
0x8c65  call     instance string Microsoft.Crm.Sandbox.TraceSettingsCache::get_TraceCategories()
0x8c6a  call     instance valuetype [System]System.Diagnostics.TraceLevel Microsoft.Crm.Sandbox.TraceSettingsCache::GetHighestTraceLevel(string specificCategory, string traceCategories)
0x8c6f  ret
```
