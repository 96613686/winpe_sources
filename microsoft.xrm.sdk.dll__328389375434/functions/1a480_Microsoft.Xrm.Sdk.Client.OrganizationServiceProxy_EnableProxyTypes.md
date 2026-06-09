# Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::EnableProxyTypes

- ea: `0x1a480`
- end: `0x1a4ac`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::EnableProxyTypes`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x186c0`

## string_xrefs

- `0x1a486`: `ServiceConfiguration`
- `0x1a49c`: `orgConfig`

## pseudocode

```c

```

## disassembly

```asm
0x1a480  ldarg.0
0x1a481  call     instance class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceConfiguration()
0x1a486  ldstr    aServiceconfigu_0// "ServiceConfiguration"
0x1a48b  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1a490  ldarg.0
0x1a491  call     instance class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceConfiguration()
0x1a496  isinst   Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration
0x1a49b  dup
0x1a49c  ldstr    aOrgconfig// "orgConfig"
0x1a4a1  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1a4a6  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::EnableProxyTypes()
0x1a4ab  ret
```
