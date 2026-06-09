# Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::TryGetTelemetryEnabledRegistryOverride

- ea: `0x4070`
- end: `0x40a5`
- name: `Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::TryGetTelemetryEnabledRegistryOverride`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4070`

## pseudocode

```c

```

## disassembly

```asm
0x4070  ldsfld   string Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::FeatureShortName
0x4075  ldstr    aEnabled// "Enabled"
0x407a  call     string [mscorlib]System.String::Concat(string, string)
0x407f  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x4084  isinst   valuetype [mscorlib]System.Nullable`1<int32>
0x4089  unbox.any valuetype [mscorlib]System.Nullable`1<int32>
0x408e  stloc.0
0x408f  ldc.i4.0
0x4090  stloc.1
0x4091  ldloca.s 0
0x4093  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x4098  ldloc.1
0x4099  bgt.s    loc_409D
0x409b  ldc.i4.0
0x409c  ret
0x409d  ldloca.s 0
0x409f  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x40a4  ret
```
