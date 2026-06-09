# Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::.ctor

- ea: `0x4020`
- end: `0x406e`
- name: `Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::.ctor`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x4e90`

## pseudocode

```c

```

## disassembly

```asm
0x4020  ldarg.0
0x4021  call     instance void [Microsoft.Crm.Core]Microsoft.Crm.FeatureDetail::.ctor()
0x4026  ldarg.0
0x4027  ldstr    aFcb// "FCB."
0x402c  ldsfld   string Microsoft.Crm.Application.Components.Shared.FeatureControl.LatencyAndBandwidthFeature::FeatureShortName
0x4031  call     string [mscorlib]System.String::Concat(string, string)
0x4036  call     instance void [Microsoft.Crm.Core]Microsoft.Crm.FeatureDetail::set_Name(string)
0x403b  ldarg.0
0x403c  ldc.i4.1
0x403d  call     instance void [Microsoft.Crm.Core]Microsoft.Crm.FeatureDetail::set_FeatureLocation(valuetype [Microsoft.Crm.Core]Microsoft.Crm.FeatureLocation)
0x4042  ldarg.0
0x4043  ldc.i4.7
0x4044  call     instance void [Microsoft.Crm.Core]Microsoft.Crm.FeatureDetail::set_ConfigSku(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku)
0x4049  ldarg.0
0x404a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureVersionDetail>::.ctor()
0x404f  dup
0x4050  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.FeatureVersionDetail::.ctor()
0x4055  dup
0x4056  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.BootstrapService::GetSku()
0x405b  ldc.i4.2
0x405c  ceq
0x405e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.FeatureVersionDetail::set_DefaultValue(bool)
0x4063  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureVersionDetail>::Add(var<u1>)
0x4068  call     instance void [Microsoft.Crm.Core]Microsoft.Crm.FeatureDetail::set_Versions(class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureVersionDetail>)
0x406d  ret
```
