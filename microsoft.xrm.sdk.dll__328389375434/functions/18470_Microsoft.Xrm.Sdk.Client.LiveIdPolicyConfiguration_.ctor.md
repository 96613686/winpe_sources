# Microsoft.Xrm.Sdk.Client.LiveIdPolicyConfiguration::.ctor

- ea: `0x18470`
- end: `0x18496`
- name: `Microsoft.Xrm.Sdk.Client.LiveIdPolicyConfiguration::.ctor`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18020`
- `0x18100`
- `0x18430`
- `0x18440`
- `0x19ba0`

## pseudocode

```c

```

## disassembly

```asm
0x18470  ldarg.0
0x18471  ldarg.1
0x18472  call     instance void Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration::.ctor(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy)
0x18477  ldarg.1
0x18478  newobj   instance void Microsoft.Xrm.Sdk.Client.LiveIdentityProviderTrustConfiguration::.ctor(class Microsoft.Xrm.Sdk.Client.AuthenticationPolicy xrmPolicy)
0x1847d  stloc.0
0x1847e  ldarg.0
0x1847f  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTypeDictionary Microsoft.Xrm.Sdk.Client.OnlinePolicyConfiguration::get_OnlineProviders()
0x18484  ldloc.0
0x18485  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_Endpoint()
0x1848a  call     class [System]System.Uri Microsoft.Xrm.Sdk.Client.Extensions::GetServiceRoot(class [System]System.Uri url)
0x1848f  ldloc.0
0x18490  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [System]System.Uri, class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration>::Add(var<u1>, !!T0)
0x18495  ret
```
