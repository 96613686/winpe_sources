# Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::IsEnabled

- ea: `0x40b0`
- end: `0x40c7`
- name: `Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::IsEnabled`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x40b0`

## pseudocode

```c

```

## disassembly

```asm
0x40b0  ldsfld   class [mscorlib]System.Lazy`1<bool> Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::lazyRegistryOverride
0x40b5  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x40ba  brfalse.s loc_40BE
0x40bc  ldc.i4.1
0x40bd  ret
0x40be  ldarg.0
0x40bf  ldarg.1
0x40c0  ldarg.2
0x40c1  call     instance bool [Microsoft.Crm.Core]Microsoft.Crm.FeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0x40c6  ret
```
