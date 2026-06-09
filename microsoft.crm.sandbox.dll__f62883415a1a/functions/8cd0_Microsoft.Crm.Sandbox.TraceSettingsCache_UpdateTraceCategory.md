# Microsoft.Crm.Sandbox.TraceSettingsCache::UpdateTraceCategory

- ea: `0x8cd0`
- end: `0x8cfd`
- name: `Microsoft.Crm.Sandbox.TraceSettingsCache::UpdateTraceCategory`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x8bc0`
- `0x8bd0`
- `0x8ca0`
- `0x8cd0`

## pseudocode

```c

```

## disassembly

```asm
0x8cd0  call     string Microsoft.Crm.Sandbox.TraceSettingsCache::GetRegistryTraceCategories()
0x8cd5  stloc.0
0x8cd6  ldloc.0
0x8cd7  brfalse.s loc_8CFC
0x8cd9  ldloc.0
0x8cda  ldarg.0
0x8cdb  call     instance string Microsoft.Crm.Sandbox.TraceSettingsCache::get_TraceCategories()
0x8ce0  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x8ce5  brfalse.s loc_8CFC
0x8ce7  ldarg.0
0x8ce8  ldloc.0
0x8ce9  call     instance void Microsoft.Crm.Sandbox.TraceSettingsCache::set_TraceCategories(string value)
0x8cee  ldarg.0
0x8cef  ldc.i4.8
0x8cf0  ldc.i4.s 0xB
0x8cf2  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel>::.ctor(int32, int32)
0x8cf7  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel> Microsoft.Crm.Sandbox.TraceSettingsCache::_traceLevels
0x8cfc  ret
```
