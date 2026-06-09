# Microsoft.Xrm.Sdk.Utility.ClaimsEndpointProviderRetriever::GetEndpointProvider

- ea: `0x590`
- end: `0x60e`
- name: `Microsoft.Xrm.Sdk.Utility.ClaimsEndpointProviderRetriever::GetEndpointProvider`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x550`
- `0x590`
- `0x5340`
- `0x5360`

## string_xrefs

- `0x5cb`: `IfdIntranetAccessEnabled`

## pseudocode

```c

```

## disassembly

```asm
0x590  ldarg.2
0x591  call     valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.EndpointAccessType Microsoft.Xrm.Sdk.Utility.EndpointProviderRetriever::GetRequestedEndpointAccessType(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.EndpointAccessType endpointAccessType)
0x596  stloc.0
0x597  ldarg.1
0x598  stloc.1
0x599  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x59e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x5a3  ldc.i4.2
0x5a4  bne.un.s loc_5AA
0x5a6  ldc.i4.1
0x5a7  stloc.1
0x5a8  br.s     loc_605
0x5aa  ldloc.0
0x5ab  ldc.i4.2
0x5ac  bne.un.s loc_5EB
0x5ae  call     class Microsoft.Crm.Authentication.WebConfigAuthenticationSettings Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::get_Instance()
0x5b3  callvirt instance bool Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::get_IfdEnabled()
0x5b8  brfalse.s loc_5EB
0x5ba  call     class [Microsoft.Crm.Core]Microsoft.Crm.IAppUtilSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.AppUtilSettingsProvider::get_Instance()
0x5bf  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IAppUtilSettingsProvider::IsPathBasedURLsEnabled()
0x5c4  brtrue.s loc_5EB
0x5c6  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x5cb  ldstr    aIfdintranetacc// "IfdIntranetAccessEnabled"
0x5d0  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider::GetDeploymentSetting(string)
0x5d5  stloc.2
0x5d6  ldloc.2
0x5d7  brfalse.s loc_5E9
0x5d9  ldloc.2
0x5da  unbox.any [mscorlib]System.Boolean
0x5df  brfalse.s loc_5E9
0x5e1  ldc.i4.0
0x5e2  ldc.i4.1
0x5e3  call     class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider [Microsoft.Crm.Core]Microsoft.Crm.WebServices.OrganizationEndpointProviderFactory::Create(int32, bool)
0x5e8  ret
0x5e9  ldnull
0x5ea  ret
0x5eb  ldloc.0
0x5ec  ldc.i4.1
0x5ed  bne.un.s loc_605
0x5ef  call     class Microsoft.Crm.Authentication.WebConfigAuthenticationSettings Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::get_Instance()
0x5f4  callvirt instance bool Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::get_IfdEnabled()
0x5f9  brfalse.s loc_603
0x5fb  ldc.i4.2
0x5fc  ldc.i4.1
0x5fd  call     class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider [Microsoft.Crm.Core]Microsoft.Crm.WebServices.OrganizationEndpointProviderFactory::Create(int32, bool)
0x602  ret
0x603  ldnull
0x604  ret
0x605  ldloc.1
0x606  ldc.i4.1
0x607  ldarg.3
0x608  call     class [Microsoft.Crm.Core]Microsoft.Crm.WebServices.IOrganizationEndpointProvider [Microsoft.Crm.Core]Microsoft.Crm.WebServices.OrganizationEndpointProviderFactory::Create(int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x60d  ret
```
