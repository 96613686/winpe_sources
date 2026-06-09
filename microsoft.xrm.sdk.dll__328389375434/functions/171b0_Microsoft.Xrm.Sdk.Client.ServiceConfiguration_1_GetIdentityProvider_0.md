# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::GetIdentityProvider_0

- ea: `0x171b0`
- end: `0x171de`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::GetIdentityProvider_0`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x171b0`
- `0x17ad0`
- `0x17b10`
- `0x18020`
- `0x19ba0`

## pseudocode

```c

```

## disassembly

```asm
0x171b0  ldarg.0
0x171b1  call     instance class Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::TryGetOnlineTrustConfiguration()
0x171b6  stloc.0
0x171b7  ldloc.0
0x171b8  brtrue.s loc_171BC
0x171ba  ldnull
0x171bb  ret
0x171bc  call     class Microsoft.Xrm.Sdk.Client.IdentityProviderLookup Microsoft.Xrm.Sdk.Client.IdentityProviderLookup::get_Instance()
0x171c1  ldloc.0
0x171c2  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_Endpoint()
0x171c7  call     class [System]System.Uri Microsoft.Xrm.Sdk.Client.Extensions::GetServiceRoot(class [System]System.Uri url)
0x171cc  ldloc.0
0x171cd  callvirt instance class [System]System.Uri Microsoft.Xrm.Sdk.Client.IdentityProviderTrustConfiguration::get_Endpoint()
0x171d2  call     class [System]System.Uri Microsoft.Xrm.Sdk.Client.Extensions::GetServiceRoot(class [System]System.Uri url)
0x171d7  ldarg.1
0x171d8  callvirt instance class Microsoft.Xrm.Sdk.Client.IdentityProvider Microsoft.Xrm.Sdk.Client.IdentityProviderLookup::GetIdentityProvider(class [System]System.Uri host, class [System]System.Uri orgIdServiceRoot, string userPrincipalName)
0x171dd  ret
```
