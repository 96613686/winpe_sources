# Microsoft.Xrm.Sdk.Client.LiveIdentityProviderTrustConfiguration::.ctor

- ea: `0x18100`
- end: `0x18159`
- name: `Microsoft.Xrm.Sdk.Client.LiveIdentityProviderTrustConfiguration::.ctor`
- size: `89`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18470`
- `0x184b0`
- `0x18530`

## callees

- `0x17fc0`
- `0x18000`
- `0x18060`
- `0x18080`
- `0x180a0`
- `0x18330`

## pseudocode

```c

```

## disassembly

```asm
0x18100  ldarg.0
0x18101  ldarg.1
0x18102  call     instance void Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::.ctor(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy)
0x18107  ldarg.0
0x18108  ldarg.0
0x18109  call     instance class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_XrmPolicy()
0x1810e  ldstr    aAppliesto// "AppliesTo"
0x18113  ldstr    asc_2C0B4// ""
0x18118  call     string Microsoft.Xrm.Sdk.Client.PolicyHelper::GetPolicyValue(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy, string elementName, string defaultValue)
0x1811d  call     instance void Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::set_AppliesTo(string value)
0x18122  ldarg.0
0x18123  ldarg.0
0x18124  call     instance class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_XrmPolicy()
0x18129  ldstr    aLivetrustlivep// "LiveTrustLivePolicy"
0x1812e  ldsfld   string Microsoft.Xrm.Sdk.Client.LiveIdAuthenticationConfiguration::DefaultPolicy
0x18133  call     string Microsoft.Xrm.Sdk.Client.PolicyHelper::GetPolicyValue(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy, string elementName, string defaultValue)
0x18138  call     instance void Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::set_Policy(string value)
0x1813d  ldarg.0
0x1813e  ldarg.0
0x1813f  call     instance class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_XrmPolicy()
0x18144  ldstr    aLiveidappliest// "LiveIdAppliesTo"
0x18149  ldstr    aHttpPassportNe// "http://Passport.NET/tb"
0x1814e  call     string Microsoft.Xrm.Sdk.Client.PolicyHelper::GetPolicyValue(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy, string elementName, string defaultValue)
0x18153  call     instance void Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::set_LiveIdAppliesTo(string value)
0x18158  ret
```
