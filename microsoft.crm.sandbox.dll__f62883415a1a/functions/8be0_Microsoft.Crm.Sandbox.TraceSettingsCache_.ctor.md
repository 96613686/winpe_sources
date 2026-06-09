# Microsoft.Crm.Sandbox.TraceSettingsCache::.ctor

- ea: `0x8be0`
- end: `0x8c03`
- name: `Microsoft.Crm.Sandbox.TraceSettingsCache::.ctor`
- size: `35`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1080`
- `0x10d0`
- `0x8c10`

## callees

- `0x8bd0`

## pseudocode

```c

```

## disassembly

```asm
0x8be0  ldarg.0
0x8be1  ldc.i4.8
0x8be2  ldc.i4.s 0xB
0x8be4  newobj   instance void class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel>::.ctor(int32, int32)
0x8be9  stfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, valuetype [System]System.Diagnostics.TraceLevel> Microsoft.Crm.Sandbox.TraceSettingsCache::_traceLevels
0x8bee  ldarg.0
0x8bef  call     instance void [mscorlib]System.Object::.ctor()
0x8bf4  ldarg.0
0x8bf5  ldarg.1
0x8bf6  call     instance void Microsoft.Crm.Sandbox.TraceSettingsCache::set_TraceCategories(string value)
0x8bfb  ldarg.0
0x8bfc  ldc.i4.0
0x8bfd  stfld    bool Microsoft.Crm.Sandbox.TraceSettingsCache::_traceDisabled
0x8c02  ret
```
