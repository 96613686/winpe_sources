# Microsoft.Crm.Etm.EtmServerConfiguration::Initialize

- ea: `0x10090`
- end: `0x1014d`
- name: `Microsoft.Crm.Etm.EtmServerConfiguration::Initialize`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xffd0`

## callees

- `0x10060`
- `0x10090`

## string_xrefs

- `0x100a2`: `ETMStatisticsUpdateEnabled`
- `0x100c4`: `ETMProviderConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x10090  ldarg.0
0x10091  ldstr    aEtmenabled// "ETMEnabled"
0x10096  ldc.i4.0
0x10097  call     T0x2B000023
0x1009c  stfld    bool Microsoft.Crm.Etm.EtmServerConfiguration::_enabled
0x100a1  ldarg.0
0x100a2  ldstr    aEtmstatisticsu// "ETMStatisticsUpdateEnabled"
0x100a7  ldc.i4.0
0x100a8  call     T0x2B000023
0x100ad  stfld    bool Microsoft.Crm.Etm.EtmServerConfiguration::_statisticsUpdateEnabled
0x100b2  ldarg.0
0x100b3  ldstr    aEtmthrottlinge// "ETMThrottlingEnabled"
0x100b8  ldc.i4.0
0x100b9  call     T0x2B000023
0x100be  stfld    bool Microsoft.Crm.Etm.EtmServerConfiguration::_throttlingEnabled
0x100c3  ldarg.0
0x100c4  ldstr    aEtmprovidercon// "ETMProviderConfiguration"
0x100c9  ldnull
0x100ca  call     T0x2B000024
0x100cf  stfld    string Microsoft.Crm.Etm.EtmServerConfiguration::_providerConfiguration
0x100d4  ldarg.0
0x100d5  ldstr    aEtmasynccollec// "ETMAsyncCollectInterval"
0x100da  ldc.i4.s 0x1E
0x100dc  call     T0x2B000020
0x100e1  stfld    int32 Microsoft.Crm.Etm.EtmServerConfiguration::_asyncCollectInterval
0x100e6  ldarg.0
0x100e7  ldstr    aEtmperfmoncoll// "ETMPerfMonCollectInterval"
0x100ec  ldc.i4.5
0x100ed  call     T0x2B000020
0x100f2  stfld    int32 Microsoft.Crm.Etm.EtmServerConfiguration::_perfMonCollectInterval
0x100f7  ldstr    aEtmperfmonenab// "ETMPerfMonEnabled"
0x100fc  ldc.i4.1
0x100fd  call     T0x2B000023
0x10102  stloc.0
0x10103  ldarg.0
0x10104  ldloc.0
0x10105  brfalse.s loc_10134
0x10107  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x1010c  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x10111  ldc.i4.2
0x10112  beq.s    loc_1012C
0x10114  ldc.i4.1
0x10115  ldstr    aAllowperfmonfo// "AllowPerfMonForOnPremise"
0x1011a  ldc.i4.0
0x1011b  box      [mscorlib]System.Int32
0x10120  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x10125  unbox.any [mscorlib]System.Int32
0x1012a  bne.un.s loc_10134
0x1012c  ldarg.0
0x1012d  call     instance bool Microsoft.Crm.Etm.EtmServerConfiguration::IsWebServerRole()
0x10132  br.s     loc_10135
0x10134  ldc.i4.0
0x10135  stfld    bool Microsoft.Crm.Etm.EtmServerConfiguration::_performanceMonitoringEnabled
0x1013a  ldarg.0
0x1013b  ldarg.0
0x1013c  ldstr    aEtmthrottlingd// "ETMThrottlingDisabled"
0x10141  ldc.i4.0
0x10142  call     T0x2B000025
0x10147  stfld    bool Microsoft.Crm.Etm.EtmServerConfiguration::_serverThrottlingDisabled
0x1014c  ret
```
