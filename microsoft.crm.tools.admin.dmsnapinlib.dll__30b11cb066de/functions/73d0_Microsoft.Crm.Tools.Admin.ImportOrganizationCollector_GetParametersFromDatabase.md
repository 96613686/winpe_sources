# Microsoft.Crm.Tools.Admin.ImportOrganizationCollector::GetParametersFromDatabase

- ea: `0x73d0`
- end: `0x7423`
- name: `Microsoft.Crm.Tools.Admin.ImportOrganizationCollector::GetParametersFromDatabase`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x73b0`

## callees

- `0x73d0`
- `0x8050`
- `0x84f0`
- `0x8720`
- `0x8bf0`
- `0x94a0`
- `0xa540`
- `0x13900`
- `0x169a0`

## string_xrefs

- `0x740a`: `install.xml`

## pseudocode

```c

```

## disassembly

```asm
0x73d0  ldarg.0
0x73d1  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0x73d6  stloc.0
0x73d7  ldarg.0
0x73d8  ldstr    aOrganizationin// "OrganizationInfo.SqlServerName"
0x73dd  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x73e2  brfalse.s loc_7422
0x73e4  ldarg.0
0x73e5  ldstr    aOrganizationin_0// "OrganizationInfo.DatabaseName"
0x73ea  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x73ef  brfalse.s loc_7422
0x73f1  ldloc.0
0x73f2  ldc.i4.1
0x73f3  call     void Microsoft.Crm.Tools.Admin.OrganizationInfo::RetrievePropertiesFromOrganizationDatabase(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo, bool throwOnError)
0x73f8  ldloc.0
0x73f9  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x73fe  ldloc.0
0x73ff  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x7404  call     valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.Tools.Admin.DBImportHelper::get_SupportedMajorVersion()
0x7409  ldc.i4.1
0x740a  ldstr    aInstallXml// "install.xml"
0x740f  call     string Microsoft.Crm.Tools.Admin.ProvisioningPath::ConstructPath(string relativePath)
0x7414  call     valuetype [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.CrmDatabaseVersionSupported Microsoft.Crm.Tools.Admin.OrganizationController::IsCrmDatabaseVersionSupported(string sqlServerName, string organizationDatabaseName, valuetype [mscorlib]System.Nullable`1<int32> supportedMajorVersion, bool recognizeUpgrade, string installXmlPath)
0x7419  ldc.i4.3
0x741a  bne.un.s loc_7422
0x741c  ldloc.0
0x741d  call     void Microsoft.Crm.Tools.Admin.OrganizationUpgrader::SetUpgradeType(class Microsoft.Crm.Tools.Admin.OrganizationInfo organizationInfo)
0x7422  ret
```
