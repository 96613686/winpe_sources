# Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::.cctor

- ea: `0x40d0`
- end: `0x410b`
- name: `Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::.cctor`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x40d0  ldstr    aLatencyandband// "LatencyAndBandwidth"
0x40d5  stsfld   string Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::FeatureShortName
0x40da  ldsfld   class <>c <>c::<>9
0x40df  ldftn    instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail <>c::<.cctor>b__9_0()
0x40e5  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail>::.ctor(object, native int)
0x40ea  newobj   instance void class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x40ef  stsfld   class [mscorlib]System.Lazy`1<class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail> Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::instanceLazy
0x40f4  ldnull
0x40f5  ldftn    bool Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::TryGetTelemetryEnabledRegistryOverride()
0x40fb  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x4100  newobj   instance void class [mscorlib]System.Lazy`1<bool>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x4105  stsfld   class [mscorlib]System.Lazy`1<bool> Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::lazyRegistryOverride
0x410a  ret
```
