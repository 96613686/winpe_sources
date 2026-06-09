# Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::IsDirectlyImportable

- ea: `0x15840`
- end: `0x1587c`
- name: `Microsoft.Crm.Tools.Admin.ImportOrganizationInstaller::IsDirectlyImportable`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x144e0`

## callees

- `0x8050`
- `0x8720`
- `0x8bf0`
- `0x9120`
- `0xa550`
- `0x13900`

## string_xrefs

- `0x15858`: `install.xml`

## pseudocode

```c

```

## disassembly

```asm
0x15840  ldarg.0
0x15841  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x15846  ldarg.0
0x15847  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x1584c  call     valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.Tools.Admin.DBImportHelper::get_SupportedMajorVersion()
0x15851  ldc.i4.1
0x15852  ldarg.0
0x15853  callvirt instance int32 Microsoft.Crm.Tools.Admin.OrganizationInfo::get_BaseLanguageCode()
0x15858  ldstr    aInstallXml// "install.xml"
0x1585d  call     string Microsoft.Crm.Tools.Admin.ProvisioningPath::ConstructPath(int32 baseLanguageCode, string relativePath)
0x15862  call     valuetype [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.CrmDatabaseVersionSupported Microsoft.Crm.Tools.Admin.OrganizationController::IsCrmDatabaseVersionSupported(string sqlServerName, string organizationDatabaseName, valuetype [mscorlib]System.Nullable`1<int32> supportedMajorVersion, bool recognizeUpgrade, string installXmlPath)
0x15867  dup
0x15868  ldc.i4.0
0x15869  cgt.un
0x1586b  ldstr    aDatabaseVersio// "Database Version is not supported.  Thi"...
0x15870  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x15875  ldc.i4.3
0x15876  ceq
0x15878  ldc.i4.0
0x15879  ceq
0x1587b  ret
```
