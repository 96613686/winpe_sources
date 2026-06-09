# Microsoft.Crm.CrmLive.Provisioning.DBInstallAction::DropDatabase

- ea: `0x6d00`
- end: `0x6e9f`
- name: `Microsoft.Crm.CrmLive.Provisioning.DBInstallAction::DropDatabase`
- size: `415`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6ab0`
- `0x187c0`

## callees

- `0x6d00`
- `0x302f0`

## string_xrefs

- `0x6daf`: `DBInstallAction_DropDatabase_`
- `0x6e09`: `DBInstallAction DropDatabase Failed`

## pseudocode

```c

```

## disassembly

```asm
0x6d00  newobj   instance void <>c__DisplayClass7_0::.ctor()
0x6d05  stloc.0
0x6d06  ldloc.0
0x6d07  ldarg.1
0x6d08  stfld    string <>c__DisplayClass7_0::databaseName
0x6d0d  ldloc.0
0x6d0e  ldfld    string <>c__DisplayClass7_0::databaseName
0x6d13  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6d18  brtrue.s loc_6D22
0x6d1a  ldarg.0
0x6d1b  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6d20  brfalse.s loc_6D37
0x6d22  ldnull
0x6d23  ldarg.3
0x6d24  ldc.i4.s 0x4A
0x6d26  ldstr    aSkipDropdataba_0// "Skip DropDatabase as the databaseName o"...
0x6d2b  ldc.i4.0
0x6d2c  newarr   [mscorlib]System.Object
0x6d31  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6d36  ret
0x6d37  ldarg.s  4
0x6d39  brfalse  loc_6E59
0x6d3e  call     T0x2B00001A
0x6d43  ldarg.3
0x6d44  ldc.i4.1
0x6d45  ldc.i4.0
0x6d46  ldloca.s 2
0x6d48  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x6d4e  ldloc.2
0x6d4f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation> [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationDatabaseLocationService::RetrieveOrganizationCurrentDatabaseDetails(valuetype [mscorlib]System.Guid, bool, bool, valuetype [mscorlib]System.Nullable`1<bool>)
0x6d54  ldloc.0
0x6d55  ldftn    instance bool <>c__DisplayClass7_0::<DropDatabase>b__0(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation x)
0x6d5b  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation, bool>::.ctor(object, native int)
0x6d60  call     T0x2B000020
0x6d65  stloc.1
0x6d66  ldloc.1
0x6d67  brfalse  loc_6E3B
0x6d6c  call     T0x2B000019
0x6d71  stloc.3
0x6d72  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanPrimaryDatabaseIdentifier::.ctor()
0x6d77  dup
0x6d78  ldloc.1
0x6d79  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation::get_Region()
0x6d7e  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_AzureRegion(string)
0x6d83  dup
0x6d84  ldloc.1
0x6d85  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation::get_ConnectionString()
0x6d8a  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_ConnectionString(string)
0x6d8f  dup
0x6d90  ldloc.1
0x6d91  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation::get_DatabaseName()
0x6d96  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_DatabaseName(string)
0x6d9b  dup
0x6d9c  ldloc.1
0x6d9d  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationDatabaseLocation::get_LogicalServer()
0x6da2  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier::set_LogicalServer(string)
0x6da7  stloc.s  4
0x6da9  ldc.i4.0
0x6daa  stloc.s  5
0x6dac  ldc.i4.0
0x6dad  stloc.s  6
0x6daf  ldstr    aDbinstallactio_0// "DBInstallAction_DropDatabase_"
0x6db4  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x6db9  box      [mscorlib]System.Guid
0x6dbe  call     string [mscorlib]System.String::Concat(object, object)
0x6dc3  stloc.s  7
0x6dc5  br.s     loc_6E35
0x6dc7  nop
0x6dc8  ldloc.3
0x6dc9  ldloc.s  7
0x6dcb  ldloc.s  4
0x6dcd  ldarg.3
0x6dce  call     valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationToken::get_None()
0x6dd3  callvirt instance class [mscorlib]System.Threading.Tasks.Task [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.ISpartanService::DropDatabaseAsync(string, class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.Spartan.SpartanDatabaseIdentifier, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Threading.CancellationToken)
0x6dd8  ldc.i4.0
0x6dd9  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable [mscorlib]System.Threading.Tasks.Task::ConfigureAwait(bool)
0x6dde  stloc.s  8
0x6de0  ldloca.s 8
0x6de2  call     instance valuetype [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable::GetAwaiter()
0x6de7  stloc.s  9
0x6de9  ldloca.s 9
0x6deb  call     instance void [mscorlib]System.Runtime.CompilerServices.ConfiguredTaskAwaitable/ConfiguredTaskAwaiter::GetResult()
0x6df0  call     T0x2B00001A
0x6df5  ldarg.3
0x6df6  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.IOrganizationDatabaseLocationService::DeleteAllOrgDatabases(valuetype [mscorlib]System.Guid)
0x6dfb  ldc.i4.1
0x6dfc  stloc.s  6
0x6dfe  leave.s  loc_6E35
0x6e00  ldloc.s  5
0x6e02  ldc.i4.1
0x6e03  add
0x6e04  stloc.s  5
0x6e06  ldarg.3
0x6e07  ldc.i4.s 0x4A
0x6e09  ldstr    aDbinstallactio_1// "DBInstallAction DropDatabase Failed"
0x6e0e  ldc.i4.0
0x6e0f  newarr   [mscorlib]System.Object
0x6e14  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6e19  ldloc.s  5
0x6e1b  ldc.i4.3
0x6e1c  blt.s    loc_6E20
0x6e1e  rethrow
0x6e20  ldc.r8   5.0
0x6e29  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x6e2e  call     void [mscorlib]System.Threading.Thread::Sleep(valuetype [mscorlib]System.TimeSpan)
0x6e33  leave.s  loc_6E35
0x6e35  ldloc.s  6
0x6e37  brfalse.s loc_6DC7
0x6e39  br.s     loc_6E65
0x6e3b  ldnull
0x6e3c  ldarg.3
0x6e3d  ldc.i4.s 0x4A
0x6e3f  ldstr    aCanTFindAnyAss// "Can’t find any associate records in Org"...
0x6e44  ldc.i4.1
0x6e45  newarr   [mscorlib]System.Object
0x6e4a  dup
0x6e4b  ldc.i4.0
0x6e4c  ldloc.0
0x6e4d  ldfld    string <>c__DisplayClass7_0::databaseName
0x6e52  stelem.ref
0x6e53  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6e58  ret
0x6e59  ldarg.0
0x6e5a  ldloc.0
0x6e5b  ldfld    string <>c__DisplayClass7_0::databaseName
0x6e60  call     void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.Helpers::DropDatabase(string, string)
0x6e65  call     class [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.AuditHistory::NewService()
0x6e6a  ldarg.3
0x6e6b  ldstr    aOrganizationId// "Organization.Id"
0x6e70  ldstr    aDropdatabase// "DropDatabase"
0x6e75  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6e7a  ldstr    aDatabase0Dropp// "Database {0} dropped successfully from "...
0x6e7f  ldc.i4.2
0x6e80  newarr   [mscorlib]System.Object
0x6e85  dup
0x6e86  ldc.i4.0
0x6e87  ldloc.0
0x6e88  ldfld    string <>c__DisplayClass7_0::databaseName
0x6e8d  stelem.ref
0x6e8e  dup
0x6e8f  ldc.i4.1
0x6e90  ldarg.0
0x6e91  stelem.ref
0x6e92  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6e97  ldc.i4.1
0x6e98  ldarg.3
0x6e99  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.IAuditHistory::CreateCompletedEntry(valuetype [mscorlib]System.Guid, string, string, string, bool, valuetype [mscorlib]System.Guid)
0x6e9e  ret
```
