# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::GetLiveTrustConfig

- ea: `0x16ed0`
- end: `0x16f0b`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::GetLiveTrustConfig`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x18430`

## string_xrefs

- `0x16f00`: `liveTrustConfig`
- `0x16edc`: `liveConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x16ed0  ldarg.0
0x16ed1  call     instance class Microsoft.Xrm.Sdk.Client.PolicyConfiguration class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_PolicyConfiguration()
0x16ed6  isinst   Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration
0x16edb  dup
0x16edc  ldstr    aLiveconfigurat// "liveConfiguration"
0x16ee1  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x16ee6  callvirt instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTypeDictionary Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration::get_OnlineProviders()
0x16eeb  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::get_Values()
0x16ef0  call     T0x2B000064
0x16ef5  call     T0x2B00001F
0x16efa  box      mvar<u1>
0x16eff  dup
0x16f00  ldstr    aLivetrustconfi// "liveTrustConfig"
0x16f05  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x16f0a  ret
```
