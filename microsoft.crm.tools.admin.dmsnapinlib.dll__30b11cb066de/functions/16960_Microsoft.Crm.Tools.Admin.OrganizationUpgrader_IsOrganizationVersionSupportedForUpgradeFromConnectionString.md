# Microsoft.Crm.Tools.Admin.OrganizationUpgrader::IsOrganizationVersionSupportedForUpgradeFromConnectionString

- ea: `0x16960`
- end: `0x16993`
- name: `Microsoft.Crm.Tools.Admin.OrganizationUpgrader::IsOrganizationVersionSupportedForUpgradeFromConnectionString`
- size: `51`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x16910`
- `0x16950`

## callees

- `0xa540`
- `0x16960`

## string_xrefs

- `0x1696a`: `install.xml`

## pseudocode

```c

```

## disassembly

```asm
0x16960  ldc.i4.0
0x16961  stloc.0
0x16962  ldarg.1
0x16963  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x16968  brfalse.s loc_16976
0x1696a  ldstr    aInstallXml// "install.xml"
0x1696f  call     string Microsoft.Crm.Tools.Admin.ProvisioningPath::ConstructPath(string relativePath)
0x16974  starg.s  1
0x16976  ldarg.0
0x16977  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDirectSqlConnection::.ctor(string)
0x1697c  stloc.1
0x1697d  ldarg.1
0x1697e  ldloc.1
0x1697f  call     bool [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::IsValidForUpgrade(string, class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x16984  stloc.0
0x16985  leave.s  loc_16991
0x16987  ldloc.1
0x16988  brfalse.s loc_16990
0x1698a  ldloc.1
0x1698b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16990  endfinally
0x16991  ldloc.0
0x16992  ret
```
