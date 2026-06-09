# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::GetOnlineTrustConfiguration

- ea: `0x16f10`
- end: `0x16f44`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::GetOnlineTrustConfiguration`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x16f10`
- `0x18430`

## string_xrefs

- `0x16f1d`: `liveFederationConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x16f10  ldarg.0
0x16f11  call     instance class Microsoft.Xrm.Sdk.Client.PolicyConfiguration class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_PolicyConfiguration()
0x16f16  isinst   Microsoft.Xrm.Sdk.Client.OnlineFederationPolicyConfiguration
0x16f1b  stloc.0
0x16f1c  ldloc.0
0x16f1d  ldstr    aLivefederation// "liveFederationConfiguration"
0x16f22  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x16f27  ldloc.0
0x16f28  callvirt instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTypeDictionary Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration::get_OnlineProviders()
0x16f2d  ldarg.1
0x16f2e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::ContainsKey(var<u1>)
0x16f33  brfalse.s loc_16F42
0x16f35  ldloc.0
0x16f36  callvirt instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTypeDictionary Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration::get_OnlineProviders()
0x16f3b  ldarg.1
0x16f3c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::get_Item(void)
0x16f41  ret
0x16f42  ldnull
0x16f43  ret
```
