# Microsoft.Crm.MultiTenantPackageDeployment.OnPremPackageDeployerWrapper::CreateCrmServiceClient

- ea: `0x1ad0`
- end: `0x1af4`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.OnPremPackageDeployerWrapper::CreateCrmServiceClient`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1ad0  call     class [System]System.Net.NetworkCredential [System]System.Net.CredentialCache::get_DefaultNetworkCredentials()
0x1ad5  ldarg.0
0x1ad6  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.OnPremPackageDeployerWrapper::_hostName
0x1adb  ldstr    asc_3022// ""
0x1ae0  ldarg.0
0x1ae1  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.OnPremPackageDeployerWrapper::_orgName
0x1ae6  ldc.i4.0
0x1ae7  ldarg.0
0x1ae8  ldfld    bool Microsoft.Crm.MultiTenantPackageDeployment.OnPremPackageDeployerWrapper::_useSSL
0x1aed  ldnull
0x1aee  newobj   instance void [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::.ctor(class [System]System.Net.NetworkCredential, string, string, string, bool, bool, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.OrganizationDetail)
0x1af3  ret
```
