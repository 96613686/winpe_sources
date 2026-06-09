# Microsoft.Crm.Sandbox.TraceSettingsCache::GetRegistryTraceCategories

- ea: `0x8ca0`
- end: `0x8cd0`
- name: `Microsoft.Crm.Sandbox.TraceSettingsCache::GetRegistryTraceCategories`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8c10`
- `0x8cd0`

## callees

- `0x8ca0`

## pseudocode

```c

```

## disassembly

```asm
0x8ca0  ldstr    aErrorWarning// "*:Error;*:Warning"
0x8ca5  stloc.0
0x8ca6  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x8cab  callvirt instance bool [mscorlib]System.AppDomain::get_IsFullyTrusted()
0x8cb0  brfalse.s loc_8CCE
0x8cb2  ldstr    aTracecategorie// "TraceCategories"
0x8cb7  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x8cbc  isinst   [mscorlib]System.String
0x8cc1  stloc.1
0x8cc2  ldloc.1
0x8cc3  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x8cc8  brfalse.s loc_8CCC
0x8cca  ldloc.0
0x8ccb  ret
0x8ccc  ldloc.1
0x8ccd  ret
0x8cce  ldloc.0
0x8ccf  ret
```
