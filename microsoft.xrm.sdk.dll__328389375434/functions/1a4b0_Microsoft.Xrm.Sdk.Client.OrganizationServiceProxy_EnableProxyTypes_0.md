# Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::EnableProxyTypes_0

- ea: `0x1a4b0`
- end: `0x1a4e8`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::EnableProxyTypes_0`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x18730`

## string_xrefs

- `0x1a4c1`: `ServiceConfiguration`
- `0x1a4d7`: `orgConfig`

## pseudocode

```c

```

## disassembly

```asm
0x1a4b0  ldarg.1
0x1a4b1  ldstr    aAssembly// "assembly"
0x1a4b6  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1a4bb  ldarg.0
0x1a4bc  call     instance class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceConfiguration()
0x1a4c1  ldstr    aServiceconfigu_0// "ServiceConfiguration"
0x1a4c6  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1a4cb  ldarg.0
0x1a4cc  call     instance class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>> class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<class Microsoft.Xrm.Sdk.IOrganizationService>::get_ServiceConfiguration()
0x1a4d1  isinst   Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration
0x1a4d6  dup
0x1a4d7  ldstr    aOrgconfig// "orgConfig"
0x1a4dc  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1a4e1  ldarg.1
0x1a4e2  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::EnableProxyTypes(class [mscorlib]System.Reflection.Assembly assembly)
0x1a4e7  ret
```
