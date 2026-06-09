# Microsoft.Crm.Tools.Admin.OrganizationInfo::RetrievePropertiesFromOrganizationDatabase

- ea: `0x94a0`
- end: `0x95da`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::RetrievePropertiesFromOrganizationDatabase`
- size: `314`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x73d0`
- `0x9320`
- `0x93b0`

## callees

- `0x8600`
- `0x8610`
- `0x8630`
- `0x8720`
- `0x8900`
- `0x89d0`
- `0x8a30`
- `0x8a50`
- `0x8bf0`
- `0x8cd0`
- `0x8d40`
- `0x9120`
- `0x9160`
- `0x94a0`
- `0x95e0`
- `0xa1d0`
- `0xa280`
- `0xa320`
- `0xa400`

## string_xrefs

- `0x95a7`: `Error occured attempting to read properties from organization database {0}.{1}:  {2}`

## pseudocode

```c

```

## disassembly

```asm
0x94a0  ldarg.0
0x94a1  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0x94a6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x94ab  brtrue   loc_95D9
0x94b0  ldarg.0
0x94b1  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x94b6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x94bb  brtrue   loc_95D9
0x94c0  ldc.i4.0
0x94c1  stloc.0
0x94c2  ldarg.0
0x94c3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x94c8  call     bool [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.SpartanUtility::IsXdbOrg(valuetype [mscorlib]System.Guid)
0x94cd  stloc.0
0x94ce  leave.s  loc_94D5
0x94d0  pop
0x94d1  ldc.i4.0
0x94d2  stloc.0
0x94d3  leave.s  loc_94D5
0x94d5  ldloc.0
0x94d6  brtrue.s loc_94E5
0x94d8  ldarg.0
0x94d9  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ConnectionString()
0x94de  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDirectSqlConnection::.ctor(string)
0x94e3  br.s     loc_94F6
0x94e5  ldarg.0
0x94e6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x94eb  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseUtility::.ctor(valuetype [mscorlib]System.Guid)
0x94f0  ldc.i4.2
0x94f1  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseUtility::GetConnection(valuetype [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.InstallDatabase)
0x94f6  stloc.1
0x94f7  ldloc.1
0x94f8  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::IsConnectionOpen()
0x94fd  brtrue.s loc_9505
0x94ff  ldloc.1
0x9500  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x9505  ldarg.0
0x9506  ldloc.1
0x9507  call     int32 Microsoft.Crm.Tools.Admin.OrganizationOperation::GetBaseLcidFromOrgDatabase(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection)
0x950c  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_BaseLanguageCode(int32 value)
0x9511  ldarg.0
0x9512  ldloc.1
0x9513  call     int32 Microsoft.Crm.Tools.Admin.OrganizationOperation::GetFullTextSearchLocaleId(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection)
0x9518  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_FullTextSearchLocaleId(int32 value)
0x951d  leave.s  loc_953E
0x951f  pop
0x9520  ldstr    aTheFulltextInd// "The FullText Indexing language code cou"...
0x9525  ldc.i4.0
0x9526  newarr   [mscorlib]System.Object
0x952b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x9530  ldarg.0
0x9531  ldarg.0
0x9532  callvirt instance int32 Microsoft.Crm.Tools.Admin.OrganizationInfo::get_BaseLanguageCode()
0x9537  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_FullTextSearchLocaleId(int32 value)
0x953c  leave.s  loc_953E
0x953e  ldarg.0
0x953f  ldloc.1
0x9540  ldarg.0
0x9541  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x9546  call     string [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.SqlUtility::GetDatabaseCollation(class [System.Data]System.Data.IDbConnection, string)
0x954b  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_OrganizationCollation(string value)
0x9550  ldnull
0x9551  ldarg.0
0x9552  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ExistingDatabaseVersion()
0x9557  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x955c  brtrue.s loc_956B
0x955e  ldarg.0
0x955f  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ExistingDatabaseVersion()
0x9564  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x9569  brtrue.s loc_9577
0x956b  ldarg.0
0x956c  ldloc.1
0x956d  call     class [mscorlib]System.Version [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.CrmServerUtility::GetCrmDatabaseVersion(class [System.Data]System.Data.IDbConnection)
0x9572  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_ExistingDatabaseVersion(class [mscorlib]System.Version value)
0x9577  ldarg.0
0x9578  ldloc.1
0x9579  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::RetrieveBaseCurrencyParameters(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection)
0x957e  ldarg.0
0x957f  dup
0x9580  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_IsXrmOrg()
0x9585  ldloc.1
0x9586  call     bool Microsoft.Crm.Tools.Admin.OrganizationOperation::CheckIfXrmOrg(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection)
0x958b  and
0x958c  callvirt instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::set_IsXrmOrg(bool value)
0x9591  leave.s  loc_959D
0x9593  ldloc.1
0x9594  brfalse.s loc_959C
0x9596  ldloc.1
0x9597  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x959c  endfinally
0x959d  leave.s  loc_95D9
0x959f  stloc.2
0x95a0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x95a5  ldc.i4.5
0x95a6  ldc.i4.2
0x95a7  ldstr    aErrorOccuredAt// "Error occured attempting to read proper"...
0x95ac  ldc.i4.3
0x95ad  newarr   [mscorlib]System.Object
0x95b2  dup
0x95b3  ldc.i4.0
0x95b4  ldarg.0
0x95b5  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerPrimary()
0x95ba  stelem.ref
0x95bb  dup
0x95bc  ldc.i4.1
0x95bd  ldarg.0
0x95be  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0x95c3  stelem.ref
0x95c4  dup
0x95c5  ldc.i4.2
0x95c6  ldloc.2
0x95c7  callvirt instance string [mscorlib]System.Object::ToString()
0x95cc  stelem.ref
0x95cd  call     void Microsoft.Crm.Tools.Admin.OrganizationOperation::LogEvent(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory category, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, object[] args)
0x95d2  ldarg.1
0x95d3  brfalse.s loc_95D7
0x95d5  rethrow
0x95d7  leave.s  loc_95D9
0x95d9  ret
```
