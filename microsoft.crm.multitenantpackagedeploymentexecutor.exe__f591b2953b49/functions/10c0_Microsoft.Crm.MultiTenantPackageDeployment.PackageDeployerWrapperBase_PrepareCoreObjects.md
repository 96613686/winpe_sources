# Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::PrepareCoreObjects

- ea: `0x10c0`
- end: `0x12fc`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::PrepareCoreObjects`
- size: `572`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0xe90`

## callees

- `0xb40`
- `0xb50`
- `0xcf0`
- `0xd30`
- `0xd50`
- `0xd70`
- `0x10c0`
- `0x1300`
- `0x1440`

## string_xrefs

- `0x11c3`: `CrmServiceClient could not be created`

## pseudocode

```c

```

## disassembly

```asm
0x10c0  ldsfld   string [mscorlib]System.String::Empty
0x10c5  stloc.0
0x10c6  ldarg.0
0x10c7  call     instance string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_FullyQualifiedPathToAssembly()
0x10cc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10d1  brfalse.s loc_112D
0x10d3  ldarg.0
0x10d4  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x10d9  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::PackageName
0x10de  ldstr    aDll// ".dll"
0x10e3  call     string [mscorlib]System.String::Concat(string, string)
0x10e8  stloc.1
0x10e9  ldarg.0
0x10ea  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x10ef  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::PackageLocation
0x10f4  ldloc.1
0x10f5  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x10fa  stloc.0
0x10fb  ldloc.0
0x10fc  call     bool [mscorlib]System.IO.File::Exists(string)
0x1101  brtrue.s loc_1134
0x1103  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1108  ldarg.0
0x1109  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x110e  ldstr    aPackageAssembl// "Package assembly {0} is not found."
0x1113  call     string [mscorlib]System.String::Concat(string, string)
0x1118  ldc.i4.1
0x1119  newarr   [mscorlib]System.Object
0x111e  dup
0x111f  ldc.i4.0
0x1120  ldloc.0
0x1121  stelem.ref
0x1122  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1127  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerException::.ctor(string message)
0x112c  throw
0x112d  ldarg.0
0x112e  call     instance string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_FullyQualifiedPathToAssembly()
0x1133  stloc.0
0x1134  ldarg.0
0x1135  ldnull
0x1136  ldloc.0
0x1137  ldarg.0
0x1138  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x113d  ldfld    bool Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::AllowPackageCodeExecution
0x1142  newobj   instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::.ctor(string, string, bool)
0x1147  stfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x114c  ldarg.0
0x114d  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x1152  ldarg.0
0x1153  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::CreateCrmServiceClient()
0x1158  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::set_CrmSvc(class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient)
0x115d  ldarg.0
0x115e  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x1163  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_CrmSvc()
0x1168  callvirt instance bool [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_IsReady()
0x116d  brtrue.s loc_11DE
0x116f  ldarg.0
0x1170  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x1175  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_CrmSvc()
0x117a  callvirt instance string [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_LastCrmError()
0x117f  ldstr    aUnableToLoginT// "Unable to Login to Dynamics CRM"
0x1184  callvirt instance bool [mscorlib]System.String::Contains(string)
0x1189  brfalse.s loc_11A6
0x118b  ldc.i4   0x7530
0x1190  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x1195  ldarg.0
0x1196  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x119b  ldarg.0
0x119c  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::CreateCrmServiceClient()
0x11a1  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::set_CrmSvc(class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient)
0x11a6  ldarg.0
0x11a7  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x11ac  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_CrmSvc()
0x11b1  callvirt instance bool [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::get_IsReady()
0x11b6  brtrue.s loc_11DE
0x11b8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11bd  ldarg.0
0x11be  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x11c3  ldstr    aCrmserviceclie// "CrmServiceClient could not be created"
0x11c8  call     string [mscorlib]System.String::Concat(string, string)
0x11cd  ldc.i4.0
0x11ce  newarr   [mscorlib]System.Object
0x11d3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11d8  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerException::.ctor(string message)
0x11dd  throw
0x11de  ldarg.0
0x11df  call     instance bool Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_IsSystemConvertedSolutionUpgrade()
0x11e4  brfalse.s loc_122E
0x11e6  ldarg.0
0x11e7  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x11ec  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::Payload
0x11f1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x11f6  brtrue.s loc_1213
0x11f8  ldarg.0
0x11f9  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x11fe  dup
0x11ff  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::Payload
0x1204  ldstr    asc_3E16// "|"
0x1209  call     string [mscorlib]System.String::Concat(string, string)
0x120e  stfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::Payload
0x1213  ldarg.0
0x1214  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x1219  dup
0x121a  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::Payload
0x121f  ldstr    aIsinternalupgr// "IsInternalUpgrade=true"
0x1224  call     string [mscorlib]System.String::Concat(string, string)
0x1229  stfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::Payload
0x122e  ldarg.0
0x122f  call     instance bool Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_IsInternalCRMAppsInstall()
0x1234  brfalse.s loc_124F
0x1236  ldarg.0
0x1237  ldarg.0
0x1238  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x123d  callvirt instance class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_CrmSvc()
0x1242  ldc.i4.1
0x1243  ldc.i4.0
0x1244  ldc.i4.0
0x1245  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x124a  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::SetConnectionTimeoutValues(class [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient crmSvcCli, valuetype [mscorlib]System.TimeSpan TimeOutToSet)
0x124f  ldarg.0
0x1250  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x1255  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::Payload
0x125a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x125f  brtrue.s loc_1277
0x1261  ldarg.0
0x1262  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x1267  ldarg.0
0x1268  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x126d  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::Payload
0x1272  callvirt instance void [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::ParseRuntimeSettingsDelimitedString(string)
0x1277  ldarg.0
0x1278  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x127d  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.ImportCustomizationLoader [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_InstallerCustomizedExentions()
0x1282  brfalse.s loc_12FB
0x1284  ldarg.0
0x1285  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x128a  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.ImportCustomizationLoader [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_InstallerCustomizedExentions()
0x128f  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.IImportExtensions [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.ImportCode.ImportCustomizationLoader::get_selectedPlugin()
0x1294  brtrue.s loc_12FB
0x1296  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x129b  ldarg.0
0x129c  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::_wrapperLogId
0x12a1  ldstr    aFailedToLoadPa// "Failed to load package {0} from {1}: {2"...
0x12a6  call     string [mscorlib]System.String::Concat(string, string)
0x12ab  ldc.i4.3
0x12ac  newarr   [mscorlib]System.Object
0x12b1  dup
0x12b2  ldc.i4.0
0x12b3  ldarg.0
0x12b4  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x12b9  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::PackageName
0x12be  stelem.ref
0x12bf  dup
0x12c0  ldc.i4.1
0x12c1  ldarg.0
0x12c2  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x12c7  ldfld    string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::PackageLocation
0x12cc  stelem.ref
0x12cd  dup
0x12ce  ldc.i4.2
0x12cf  ldarg.0
0x12d0  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x12d5  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_Logger()
0x12da  callvirt instance string [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastError()
0x12df  stelem.ref
0x12e0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x12e5  ldarg.0
0x12e6  ldfld    class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::coreObjects
0x12eb  callvirt instance class [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageCore.Models.CoreObjects::get_Logger()
0x12f0  callvirt instance class [mscorlib]System.Exception [Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase]Microsoft.Xrm.Tooling.PackageDeployment.CrmPackageExtentionBase.TraceLogger::get_LastException()
0x12f5  newobj   instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x12fa  throw
0x12fb  ret
```
