# Microsoft.Xrm.Sdk.Client.OrgIdentityProviderTrustConfiguration::.ctor

- ea: `0x181a0`
- end: `0x181f9`
- name: `Microsoft.Xrm.Sdk.Client.OrgIdentityProviderTrustConfiguration::.ctor`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x184b0`

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
0x181a0  ldarg.0
0x181a1  ldarg.1
0x181a2  call     instance void Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::.ctor(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy)
0x181a7  ldarg.0
0x181a8  ldarg.0
0x181a9  call     instance class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_XrmPolicy()
0x181ae  ldstr    aOrgidappliesto// "OrgIdAppliesTo"
0x181b3  ldstr    asc_2C0B4// ""
0x181b8  call     string Microsoft.Xrm.Sdk.Client.PolicyHelper::GetPolicyValue(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy, string elementName, string defaultValue)
0x181bd  call     instance void Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::set_AppliesTo(string value)
0x181c2  ldarg.0
0x181c3  ldarg.0
0x181c4  call     instance class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_XrmPolicy()
0x181c9  ldstr    aOrgidpolicy// "OrgIdPolicy"
0x181ce  ldsfld   string Microsoft.Xrm.Sdk.Client.LiveIdAuthenticationConfiguration::DefaultPolicy
0x181d3  call     string Microsoft.Xrm.Sdk.Client.PolicyHelper::GetPolicyValue(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy, string elementName, string defaultValue)
0x181d8  call     instance void Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::set_Policy(string value)
0x181dd  ldarg.0
0x181de  ldarg.0
0x181df  call     instance class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_XrmPolicy()
0x181e4  ldstr    aOrgiddeviceapp// "OrgIdDeviceAppliesTo"
0x181e9  ldstr    aHttpPassportNe// "http://Passport.NET/tb"
0x181ee  call     string Microsoft.Xrm.Sdk.Client.PolicyHelper::GetPolicyValue(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy, string elementName, string defaultValue)
0x181f3  call     instance void Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::set_LiveIdAppliesTo(string value)
0x181f8  ret
```
