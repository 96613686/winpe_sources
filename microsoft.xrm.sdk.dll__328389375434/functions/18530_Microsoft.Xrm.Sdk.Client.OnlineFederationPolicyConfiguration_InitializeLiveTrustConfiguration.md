# Microsoft.Xrm.Sdk.Client.OnlineFederationPolicyConfiguration::InitializeLiveTrustConfiguration

- ea: `0x18530`
- end: `0x185f9`
- name: `Microsoft.Xrm.Sdk.Client.OnlineFederationPolicyConfiguration::InitializeLiveTrustConfiguration`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x15c60`
- `0x15ce0`
- `0x17a30`
- `0x18100`
- `0x18260`
- `0x18430`
- `0x18530`

## pseudocode

```c

```

## disassembly

```asm
0x18530  ldarg.0
0x18531  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTypeDictionary Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration::get_OnlineProviders()
0x18536  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::get_Values()
0x1853b  call     T0x2B000061
0x18540  call     T0x2B000062
0x18545  stloc.0
0x18546  ldloc.0
0x18547  brtrue.s loc_1854A
0x18549  ret
0x1854a  ldloc.0
0x1854b  callvirt instance string Microsoft.Xrm.Sdk.Client.OrgIdentityProviderTrustConfiguration::get_LivePartnerIdentifier()
0x18550  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x18555  brfalse.s loc_18558
0x18557  ret
0x18558  ldarg.0
0x18559  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTypeDictionary Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration::get_OnlineProviders()
0x1855e  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::get_Values()
0x18563  call     T0x2B000065
0x18568  call     T0x2B000066
0x1856d  brfalse.s loc_18570
0x1856f  ret
0x18570  ldarg.0
0x18571  ldfld    object Microsoft.Xrm.Sdk.Client.OnlineFederationPolicyConfiguration::_lockObject
0x18576  stloc.1
0x18577  ldc.i4.0
0x18578  stloc.2
0x18579  ldloc.1
0x1857a  ldloca.s 2
0x1857c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x18581  ldarg.0
0x18582  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTypeDictionary Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration::get_OnlineProviders()
0x18587  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::get_Values()
0x1858c  call     T0x2B000065
0x18591  call     T0x2B000066
0x18596  brfalse.s loc_1859A
0x18598  leave.s  loc_185F8
0x1859a  newobj   instance void Microsoft.Xrm.Sdk.Client.AuthenticationPolicy::.ctor()
0x1859f  dup
0x185a0  callvirt instance class Microsoft.Xrm.Sdk.Client.PolicyDictionary Microsoft.Xrm.Sdk.Client.XrmPolicy::get_PolicyElements()
0x185a5  ldstr    aAppliesto// "AppliesTo"
0x185aa  ldloc.0
0x185ab  callvirt instance string Microsoft.Xrm.Sdk.Client.OrgIdentityProviderTrustConfiguration::get_LivePartnerIdentifier()
0x185b0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x185b5  ldarg.1
0x185b6  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.IdentityProvider::get_ServiceUrl()
0x185bb  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x185c0  stloc.3
0x185c1  dup
0x185c2  callvirt instance class Microsoft.Xrm.Sdk.Client.PolicyDictionary Microsoft.Xrm.Sdk.Client.XrmPolicy::get_PolicyElements()
0x185c7  ldstr    aLiveendpoint// "LiveEndpoint"
0x185cc  ldloc.3
0x185cd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x185d2  newobj   instance void Microsoft.Xrm.Sdk.Client.LiveIdentityProviderTrustConfiguration::.ctor(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy)
0x185d7  stloc.s  4
0x185d9  ldarg.0
0x185da  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTypeDictionary Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration::get_OnlineProviders()
0x185df  ldloc.3
0x185e0  newobj   instance void [System]System.Uri::.ctor(string)
0x185e5  ldloc.s  4
0x185e7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::Add(var<u1>, !!T0)
0x185ec  leave.s  loc_185F8
0x185ee  ldloc.2
0x185ef  brfalse.s loc_185F7
0x185f1  ldloc.1
0x185f2  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x185f7  endfinally
0x185f8  ret
```
