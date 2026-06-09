# Microsoft.Crm.Tools.Admin.InstallDatabaseAction::Do

- ea: `0x10960`
- end: `0x10a30`
- name: `Microsoft.Crm.Tools.Admin.InstallDatabaseAction::Do`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x71c0`
- `0x84f0`
- `0x8630`
- `0x8890`
- `0x8990`
- `0x89d0`
- `0x8bf0`
- `0x8e30`
- `0x9120`
- `0xa550`
- `0x10960`

## string_xrefs

- `0x1097f`: `install.xml`
- `0x109b8`: `FullText support for {0} is not installed on {1}.  Using default`

## pseudocode

```c

```

## disassembly

```asm
0x10960  ldarg.1
0x10961  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0x10966  stloc.0
0x10967  ldarg.0
0x10968  call     instance class Microsoft.Crm.Tools.Admin.OrganizationOperation Microsoft.Crm.Tools.Admin.OrganizationAction::get_OperationBase()
0x1096d  newobj   instance void [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.DatabaseInstallerLog::.ctor(class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer)
0x10972  stloc.1
0x10973  ldloc.1
0x10974  callvirt instance void [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.DatabaseInstallerLog::HookEvents()
0x10979  ldloc.0
0x1097a  callvirt instance int32 Microsoft.Crm.Tools.Admin.OrganizationInfo::get_BaseLanguageCode()
0x1097f  ldstr    aInstallXml// "install.xml"
0x10984  call     string Microsoft.Crm.Tools.Admin.ProvisioningPath::ConstructPath(int32 baseLanguageCode, string relativePath)
0x10989  stloc.2
0x1098a  ldloc.0
0x1098b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x10990  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.ServerDatabaseInstaller::.ctor(valuetype [mscorlib]System.Guid)
0x10995  stloc.3
0x10996  ldloc.0
0x10997  callvirt instance int32 Microsoft.Crm.Tools.Admin.OrganizationInfo::get_FullTextSearchLocaleId()
0x1099c  ldc.i4.m1
0x1099d  beq.s    loc_109E6
0x1099f  ldloc.0
0x109a0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x109a5  ldloc.0
0x109a6  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x109ab  ldloc.0
0x109ac  callvirt instance int32 Microsoft.Crm.Tools.Admin.OrganizationInfo::get_FullTextSearchLocaleId()
0x109b1  call     bool [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.SqlUtility::IsWordBreakerInstalledForLang(valuetype [mscorlib]System.Guid, string, int32)
0x109b6  brtrue.s loc_109E6
0x109b8  ldstr    aFulltextSuppor// "FullText support for {0} is not install"...
0x109bd  ldc.i4.2
0x109be  newarr   [mscorlib]System.Object
0x109c3  dup
0x109c4  ldc.i4.0
0x109c5  ldloc.0
0x109c6  callvirt instance int32 Microsoft.Crm.Tools.Admin.OrganizationInfo::get_FullTextSearchLocaleId()
0x109cb  box      [mscorlib]System.Int32
0x109d0  stelem.ref
0x109d1  dup
0x109d2  ldc.i4.1
0x109d3  ldloc.0
0x109d4  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x109d9  stelem.ref
0x109da  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x109df  ldloc.0
0x109e0  ldc.i4.m1
0x109e1  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_FullTextSearchLocaleId(int32 value)
0x109e6  ldloc.3
0x109e7  ldloc.0
0x109e8  callvirt instance int32 Microsoft.Crm.Tools.Admin.OrganizationInfo::get_FullTextSearchLocaleId()
0x109ed  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::set_LocalIdForFullTextSearch(int32)
0x109f2  ldloc.0
0x109f3  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x109f8  ldstr    aOrganizationin_9// "OrganizationInfo.OrganizationCollation"
0x109fd  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x10a02  brfalse.s loc_10A10
0x10a04  ldloc.3
0x10a05  ldloc.0
0x10a06  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationCollation()
0x10a0b  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::set_CollationName(string)
0x10a10  ldloc.3
0x10a11  ldloc.0
0x10a12  callvirt instance int32 Microsoft.Crm.Tools.Admin.OrganizationInfo::get_BaseLanguageCode()
0x10a17  ldloc.2
0x10a18  ldc.i4.1
0x10a19  ldloc.0
0x10a1a  callvirt instance valuetype [Microsoft.Crm.Setup.Database.Common]Microsoft.Crm.Setup.Database.Common.OrganizationOperationType Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OperationType()
0x10a1f  ceq
0x10a21  ldc.i4.0
0x10a22  ceq
0x10a24  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::Install(int32, string, bool)
0x10a29  ldloc.1
0x10a2a  callvirt instance void [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.DatabaseInstallerLog::UnhookEvents()
0x10a2f  ret
```
