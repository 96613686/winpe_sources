# Microsoft.Xrm.Sdk.Client.OnlineFederationPolicyConfiguration::.ctor

- ea: `0x184b0`
- end: `0x1852d`
- name: `Microsoft.Xrm.Sdk.Client.OnlineFederationPolicyConfiguration::.ctor`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16900`

## callees

- `0x18020`
- `0x18100`
- `0x181a0`
- `0x18330`
- `0x18430`
- `0x18440`
- `0x184b0`
- `0x19ba0`

## pseudocode

```c

```

## disassembly

```asm
0x184b0  ldarg.0
0x184b1  newobj   instance void [mscorlib]System.Object::.ctor()
0x184b6  stfld    object Microsoft.Xrm.Sdk.Client.OnlineFederationPolicyConfiguration::_lockObject
0x184bb  ldarg.0
0x184bc  ldarg.1
0x184bd  call     instance void Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration::.ctor(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy)
0x184c2  ldarg.1
0x184c3  ldstr    aLivetrustlivep// "LiveTrustLivePolicy"
0x184c8  ldsfld   string [mscorlib]System.String::Empty
0x184cd  call     string Microsoft.Xrm.Sdk.Client.PolicyHelper::GetPolicyValue(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy, string elementName, string defaultValue)
0x184d2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x184d7  brtrue.s loc_184F7
0x184d9  ldarg.1
0x184da  newobj   instance void Microsoft.Xrm.Sdk.Client.LiveIdentityProviderTrustConfiguration::.ctor(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy)
0x184df  stloc.0
0x184e0  ldarg.0
0x184e1  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTypeDictionary Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration::get_OnlineProviders()
0x184e6  ldloc.0
0x184e7  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_Endpoint()
0x184ec  call     class [System]System.Uri Microsoft.Xrm.Sdk.Client.Extensions::GetServiceRoot(class [System]System.Uri url)
0x184f1  ldloc.0
0x184f2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::Add(var<u1>, !!T0)
0x184f7  ldarg.1
0x184f8  ldstr    aOrgidpolicy// "OrgIdPolicy"
0x184fd  ldsfld   string [mscorlib]System.String::Empty
0x18502  call     string Microsoft.Xrm.Sdk.Client.PolicyHelper::GetPolicyValue(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy, string elementName, string defaultValue)
0x18507  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1850c  brtrue.s loc_1852C
0x1850e  ldarg.1
0x1850f  newobj   instance void Microsoft.Xrm.Sdk.Client.OrgIdentityProviderTrustConfiguration::.ctor(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy)
0x18514  stloc.1
0x18515  ldarg.0
0x18516  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTypeDictionary Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration::get_OnlineProviders()
0x1851b  ldloc.1
0x1851c  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_Endpoint()
0x18521  call     class [System]System.Uri Microsoft.Xrm.Sdk.Client.Extensions::GetServiceRoot(class [System]System.Uri url)
0x18526  ldloc.1
0x18527  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::Add(var<u1>, !!T0)
0x1852c  ret
```
