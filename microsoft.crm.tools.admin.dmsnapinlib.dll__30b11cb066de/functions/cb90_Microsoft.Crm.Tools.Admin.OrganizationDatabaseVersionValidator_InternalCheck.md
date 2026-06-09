# Microsoft.Crm.Tools.Admin.OrganizationDatabaseVersionValidator::InternalCheck

- ea: `0xcb90`
- end: `0xcc32`
- name: `Microsoft.Crm.Tools.Admin.OrganizationDatabaseVersionValidator::InternalCheck`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x22e0`
- `0x8050`
- `0x84f0`
- `0x8720`
- `0x89f0`
- `0x8bf0`
- `0x9120`
- `0xa550`
- `0xcb90`
- `0x13900`

## string_xrefs

- `0xcbd6`: `install.xml`
- `0xcb9d`: `InstallInfo.CreateDatabase`
- `0xcbb1`: `Cannot call this OrganizationDatabaseVersionValidator if CreateDatabase property is set to true`

## pseudocode

```c

```

## disassembly

```asm
0xcb90  ldarg.1
0xcb91  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xcb96  stloc.0
0xcb97  ldloc.0
0xcb98  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0xcb9d  ldstr    aInstallinfoCre// "InstallInfo.CreateDatabase"
0xcba2  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0xcba7  brfalse.s loc_CBBC
0xcba9  ldloc.0
0xcbaa  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_CreateDatabase()
0xcbaf  brfalse.s loc_CBBC
0xcbb1  ldstr    aCannotCallThis_1// "Cannot call this OrganizationDatabaseVe"...
0xcbb6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0xcbbb  throw
0xcbbc  ldloc.0
0xcbbd  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0xcbc2  ldloc.0
0xcbc3  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0xcbc8  stloc.1
0xcbc9  ldloc.1
0xcbca  call     valuetype [mscorlib]System.Nullable`1<int32> Microsoft.Crm.Tools.Admin.DBImportHelper::get_SupportedMajorVersion()
0xcbcf  ldc.i4.1
0xcbd0  ldloc.0
0xcbd1  callvirt instance int32 Microsoft.Crm.Tools.Admin.OrganizationInfo::get_BaseLanguageCode()
0xcbd6  ldstr    aInstallXml// "install.xml"
0xcbdb  call     string Microsoft.Crm.Tools.Admin.ProvisioningPath::ConstructPath(int32 baseLanguageCode, string relativePath)
0xcbe0  call     valuetype [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.CrmDatabaseVersionSupported Microsoft.Crm.Tools.Admin.OrganizationController::IsCrmDatabaseVersionSupported(string sqlServerName, string organizationDatabaseName, valuetype [mscorlib]System.Nullable`1<int32> supportedMajorVersion, bool recognizeUpgrade, string installXmlPath)
0xcbe5  stloc.2
0xcbe6  ldloc.2
0xcbe7  switch   loc_CBFE, loc_CC15, loc_CC15, loc_CC15
0xcbfc  br.s     loc_CC1C
0xcbfe  ldc.i4.2
0xcbff  ldstr    aOrganizationda_2// "OrganizationDatabaseVersionValidator.Fa"...
0xcc04  ldc.i4.0
0xcc05  newarr   [mscorlib]System.Object
0xcc0a  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0xcc0f  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0xcc14  ret
0xcc15  ldc.i4.0
0xcc16  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0xcc1b  ret
0xcc1c  ldstr    aDatabaseversio// "databaseVersionSupported"
0xcc21  ldloc.2
0xcc22  box      [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.CrmDatabaseVersionSupported
0xcc27  ldstr    aUnknownValueFo_0// "Unknown value for enum type CrmDatabase"...
0xcc2c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentOutOfRangeException::.ctor(string, object, string)
0xcc31  throw
```
