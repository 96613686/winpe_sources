# Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::get_Instance

- ea: `0x4000`
- end: `0x400b`
- name: `Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::get_Instance`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4010`

## pseudocode

```c

```

## disassembly

```asm
0x4000  ldsfld   class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail> Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::instanceLazy
0x4005  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail>::get_Value()
0x400a  ret
```
