# Microsoft.Crm.Sandbox.TraceSettingsCache::.ctor_0

- ea: `0x8c10`
- end: `0x8c39`
- name: `Microsoft.Crm.Sandbox.TraceSettingsCache::.ctor_0`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1790`

## callees

- `0x8be0`
- `0x8c10`
- `0x8ca0`

## pseudocode

```c

```

## disassembly

```asm
0x8c10  ldarg.0
0x8c11  call     string Microsoft.Crm.Sandbox.TraceSettingsCache::GetRegistryTraceCategories()
0x8c16  call     instance void Microsoft.Crm.Sandbox.TraceSettingsCache::.ctor(string traceCategories)
0x8c1b  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x8c20  callvirt instance bool [mscorlib]System.AppDomain::get_IsFullyTrusted()
0x8c25  brfalse.s loc_8C38
0x8c27  ldarg.0
0x8c28  ldftn    instance void Microsoft.Crm.Sandbox.TraceSettingsCache::UpdateTraceCategory(object sender, class [mscorlib]System.EventArgs e)
0x8c2e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.RegistryKeyChangedEventHandler::.ctor(object, native int)
0x8c33  call     void [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::RegisterEventHandler(class [Microsoft.Crm.Core]Microsoft.Crm.RegistryKeyChangedEventHandler)
0x8c38  ret
```
