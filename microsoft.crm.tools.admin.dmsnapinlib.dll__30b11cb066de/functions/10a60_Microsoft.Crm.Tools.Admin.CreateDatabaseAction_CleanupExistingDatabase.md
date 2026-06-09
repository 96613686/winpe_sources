# Microsoft.Crm.Tools.Admin.CreateDatabaseAction::CleanupExistingDatabase

- ea: `0x10a60`
- end: `0x10b35`
- name: `Microsoft.Crm.Tools.Admin.CreateDatabaseAction::CleanupExistingDatabase`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10a50`

## callees

- `0x71d0`
- `0x8630`
- `0x10a60`

## string_xrefs

- `0x10a89`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\DatabaseConfiguration.cs`

## pseudocode

```c

```

## disassembly

```asm
0x10a60  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x10a65  stloc.0
0x10a66  ldarg.0
0x10a67  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationAction::get_OrganizationInfo()
0x10a6c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x10a71  stloc.1
0x10a72  ldloc.0
0x10a73  ldstr    aOrganization// "Organization"
0x10a78  ldloc.1
0x10a79  box      [mscorlib]System.Guid
0x10a7e  ldnull
0x10a7f  ldc.i4   0x18B
0x10a84  ldstr    aCleanupexistin// "CleanupExistingDatabase"
0x10a89  ldstr    aDDbsShDccm2110_9// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x10a8e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x10a93  stloc.2
0x10a94  ldloc.2
0x10a95  brtrue.s loc_10A9C
0x10a97  leave    loc_10B34
0x10a9c  ldloc.2
0x10a9d  ldstr    aSqlservername// "SqlServerName"
0x10aa2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x10aa7  castclass [mscorlib]System.String
0x10aac  stloc.3
0x10aad  ldnull
0x10aae  stloc.s  4
0x10ab0  ldloc.2
0x10ab1  ldstr    aMirroredsqlser// "MirroredSqlServerName"
0x10ab6  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x10abb  brfalse.s loc_10ACF
0x10abd  ldloc.2
0x10abe  ldstr    aMirroredsqlser// "MirroredSqlServerName"
0x10ac3  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x10ac8  castclass [mscorlib]System.String
0x10acd  stloc.s  4
0x10acf  ldloc.2
0x10ad0  ldstr    aDatabasename// "DatabaseName"
0x10ad5  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x10ada  castclass [mscorlib]System.String
0x10adf  stloc.s  5
0x10ae1  ldloc.1
0x10ae2  ldc.i4.s 0xA
0x10ae4  ldstr    aInCleanupexist// "In CleanupExistingDatabase, Organizatio"...
0x10ae9  ldc.i4.4
0x10aea  newarr   [mscorlib]System.Object
0x10aef  dup
0x10af0  ldc.i4.0
0x10af1  ldloc.1
0x10af2  box      [mscorlib]System.Guid
0x10af7  stelem.ref
0x10af8  dup
0x10af9  ldc.i4.1
0x10afa  ldloc.s  5
0x10afc  stelem.ref
0x10afd  dup
0x10afe  ldc.i4.2
0x10aff  ldloc.3
0x10b00  stelem.ref
0x10b01  dup
0x10b02  ldc.i4.3
0x10b03  ldloc.s  4
0x10b05  stelem.ref
0x10b06  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x10b0b  ldloc.s  4
0x10b0d  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x10b12  brfalse.s loc_10B1E
0x10b14  ldloc.3
0x10b15  ldloc.s  5
0x10b17  call     void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.Helpers::DropDatabase(string, string)
0x10b1c  leave.s  loc_10B34
0x10b1e  ldloc.3
0x10b1f  ldloc.s  4
0x10b21  ldloc.s  5
0x10b23  call     void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.Helpers::DropMirroredDatabases(string, string, string)
0x10b28  leave.s  loc_10B34
0x10b2a  ldloc.0
0x10b2b  brfalse.s loc_10B33
0x10b2d  ldloc.0
0x10b2e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10b33  endfinally
0x10b34  ret
```
