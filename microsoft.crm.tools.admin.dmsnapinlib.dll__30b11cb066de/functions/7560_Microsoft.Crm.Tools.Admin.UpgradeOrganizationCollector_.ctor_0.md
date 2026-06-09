# Microsoft.Crm.Tools.Admin.UpgradeOrganizationCollector::.ctor_0

- ea: `0x7560`
- end: `0x7578`
- name: `Microsoft.Crm.Tools.Admin.UpgradeOrganizationCollector::.ctor_0`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x7300`
- `0xa550`

## string_xrefs

- `0x7568`: `install.xml`

## pseudocode

```c

```

## disassembly

```asm
0x7560  ldarg.0
0x7561  call     instance void Microsoft.Crm.Tools.Admin.ExistingOrganizationCollector::.ctor()
0x7566  ldarg.0
0x7567  ldarg.1
0x7568  ldstr    aInstallXml// "install.xml"
0x756d  call     string Microsoft.Crm.Tools.Admin.ProvisioningPath::ConstructPath(int32 baseLanguageCode, string relativePath)
0x7572  stfld    string Microsoft.Crm.Tools.Admin.UpgradeOrganizationCollector::_orgDatabaseInstallFilePath
0x7577  ret
```
