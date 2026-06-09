# Microsoft.Crm.PackageDeployment.OnPremPackageDeployerWrapper::CreateCrmServiceClient

- ea: `0x12c0`
- end: `0x12e4`
- name: `Microsoft.Crm.PackageDeployment.OnPremPackageDeployerWrapper::CreateCrmServiceClient`
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
0x12c0  call     class [System]System.Net.NetworkCredential [System]System.Net.CredentialCache::get_DefaultNetworkCredentials()
0x12c5  ldarg.0
0x12c6  ldfld    string Microsoft.Crm.PackageDeployment.OnPremPackageDeployerWrapper::_hostName
0x12cb  ldstr    asc_2F24// ""
0x12d0  ldarg.0
0x12d1  ldfld    string Microsoft.Crm.PackageDeployment.OnPremPackageDeployerWrapper::_orgName
0x12d6  ldc.i4.0
0x12d7  ldarg.0
0x12d8  ldfld    bool Microsoft.Crm.PackageDeployment.OnPremPackageDeployerWrapper::_useSSL
0x12dd  ldnull
0x12de  newobj   instance void [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::.ctor(class [System]System.Net.NetworkCredential, string, string, string, bool, bool, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.OrganizationDetail)
0x12e3  ret
```
