# Microsoft.Xrm.Sdk.Client.ServiceProxy`1::AuthenticateCrossRealmCore

- ea: `0x1b810`
- end: `0x1b89b`
- name: `Microsoft.Xrm.Sdk.Client.ServiceProxy`1::AuthenticateCrossRealmCore`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x7cb0`
- `0x183c0`
- `0x1b810`

## string_xrefs

- `0x1b816`: `ServiceConfiguration`
- `0x1b826`: `HomeRealmUri`
- `0x1b843`: `ServiceConfiguration.PolicyConfiguration`
- `0x1b85d`: `ServiceConfiguration.PolicyConfiguration.SecureTokenServiceIdentifier`

## pseudocode

```c

```

## disassembly

```asm
0x1b810  ldarg.0
0x1b811  call     instance class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ServiceConfiguration()
0x1b816  ldstr    aServiceconfigu_0// "ServiceConfiguration"
0x1b81b  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1b820  ldarg.0
0x1b821  call     instance class [System]System.Uri class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_HomeRealmUri()
0x1b826  ldstr    aHomerealmuri// "HomeRealmUri"
0x1b82b  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1b830  ldarg.0
0x1b831  call     instance string class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_AppliesTo()
0x1b836  brtrue.s loc_1B87D
0x1b838  ldarg.0
0x1b839  call     instance class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ServiceConfiguration()
0x1b83e  callvirt instance class Microsoft.Xrm.Sdk.Client.PolicyConfiguration class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>>::get_PolicyConfiguration()
0x1b843  ldstr    aServiceconfigu_2// "ServiceConfiguration.PolicyConfiguratio"...
0x1b848  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1b84d  ldarg.0
0x1b84e  call     instance class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ServiceConfiguration()
0x1b853  callvirt instance class Microsoft.Xrm.Sdk.Client.PolicyConfiguration class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>>::get_PolicyConfiguration()
0x1b858  callvirt instance string Microsoft.Xrm.Sdk.Client.PolicyConfiguration::get_SecureTokenServiceIdentifier()
0x1b85d  ldstr    aServiceconfigu_3// "ServiceConfiguration.PolicyConfiguratio"...
0x1b862  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNullOrEmpty(string parameter, string name)
0x1b867  ldarg.0
0x1b868  ldarg.0
0x1b869  call     instance class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ServiceConfiguration()
0x1b86e  callvirt instance class Microsoft.Xrm.Sdk.Client.PolicyConfiguration class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>>::get_PolicyConfiguration()
0x1b873  callvirt instance string Microsoft.Xrm.Sdk.Client.PolicyConfiguration::get_SecureTokenServiceIdentifier()
0x1b878  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::set_AppliesTo(string)
0x1b87d  ldarg.0
0x1b87e  call     instance class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ServiceConfiguration()
0x1b883  ldarg.0
0x1b884  call     instance class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_ClientCredentials()
0x1b889  ldarg.0
0x1b88a  call     instance string class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_AppliesTo()
0x1b88f  ldarg.0
0x1b890  call     instance class [System]System.Uri class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_HomeRealmUri()
0x1b895  callvirt instance class Microsoft.Xrm.Sdk.Client.SecurityTokenResponse class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>>::AuthenticateCrossRealm(class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials, string, class [System]System.Uri)
0x1b89a  ret
```
