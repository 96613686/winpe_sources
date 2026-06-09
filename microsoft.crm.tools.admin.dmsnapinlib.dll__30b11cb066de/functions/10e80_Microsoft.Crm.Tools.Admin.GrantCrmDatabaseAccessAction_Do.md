# Microsoft.Crm.Tools.Admin.GrantCrmDatabaseAccessAction::Do

- ea: `0x10e80`
- end: `0x10f5f`
- name: `Microsoft.Crm.Tools.Admin.GrantCrmDatabaseAccessAction::Do`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x22e0`
- `0x84f0`
- `0x8630`
- `0x8890`
- `0x8ab0`
- `0x8c70`
- `0x9010`
- `0x9060`
- `0x90b0`
- `0x10e80`
- `0x10f60`

## string_xrefs

- `0x10f2b`: `GrantDatabaseAccessAction.MultipleDCsPrompt`

## pseudocode

```c

```

## disassembly

```asm
0x10e80  ldarg.1
0x10e81  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0x10e86  stloc.0
0x10e87  ldloc.0
0x10e88  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x10e8d  call     bool [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.SpartanUtility::IsXdbOrg(valuetype [mscorlib]System.Guid)
0x10e92  brfalse.s loc_10ED1
0x10e94  ldloc.0
0x10e95  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x10e9a  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseUtility::.ctor(valuetype [mscorlib]System.Guid)
0x10e9f  stloc.1
0x10ea0  ldloc.1
0x10ea1  ldloc.0
0x10ea2  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationCollation()
0x10ea7  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseUtility::Open(string)
0x10eac  ldloc.1
0x10ead  ldloc.0
0x10eae  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlAccessGroup()
0x10eb3  ldloc.0
0x10eb4  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingGroup()
0x10eb9  ldloc.0
0x10eba  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_PrivReportingGroup()
0x10ebf  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseUtility::GrantAccessXdb(string, string, string)
0x10ec4  leave.s  loc_10ED0
0x10ec6  ldloc.1
0x10ec7  brfalse.s loc_10ECF
0x10ec9  ldloc.1
0x10eca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10ecf  endfinally
0x10ed0  ret
0x10ed1  nop
0x10ed2  ldloc.0
0x10ed3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x10ed8  newobj   instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseUtility::.ctor(valuetype [mscorlib]System.Guid)
0x10edd  stloc.2
0x10ede  ldloc.2
0x10edf  ldloc.0
0x10ee0  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationCollation()
0x10ee5  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseUtility::Open(string)
0x10eea  ldloc.2
0x10eeb  ldloc.0
0x10eec  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlAccessGroup()
0x10ef1  ldloc.0
0x10ef2  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingGroup()
0x10ef7  ldloc.0
0x10ef8  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_PrivReportingGroup()
0x10efd  callvirt instance void [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseUtility::GrantAccess(string, string, string)
0x10f02  leave.s  loc_10F0E
0x10f04  ldloc.2
0x10f05  brfalse.s loc_10F0D
0x10f07  ldloc.2
0x10f08  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10f0d  endfinally
0x10f0e  leave.s  loc_10F42
0x10f10  stloc.3
0x10f11  ldc.i4   0x3C29
0x10f16  ldloc.3
0x10f17  callvirt instance class [System.Data]System.Data.SqlClient.SqlErrorCollection [System.Data]System.Data.SqlClient.SqlException::get_Errors()
0x10f1c  ldc.i4.0
0x10f1d  callvirt instance class [System.Data]System.Data.SqlClient.SqlError [System.Data]System.Data.SqlClient.SqlErrorCollection::get_Item(int32)
0x10f22  callvirt instance int32 [System.Data]System.Data.SqlClient.SqlError::get_Number()
0x10f27  beq.s    loc_10F2B
0x10f29  rethrow
0x10f2b  ldstr    aGrantdatabasea// "GrantDatabaseAccessAction.MultipleDCsPr"...
0x10f30  ldc.i4.0
0x10f31  newarr   [mscorlib]System.Object
0x10f36  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x10f3b  ldloc.3
0x10f3c  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.SetupException::.ctor(string, class [mscorlib]System.Exception)
0x10f41  throw
0x10f42  ldloc.0
0x10f43  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x10f48  ldloc.0
0x10f49  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerMachineName()
0x10f4e  ldloc.0
0x10f4f  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x10f54  newobj   instance void [System]System.Uri::.ctor(string)
0x10f59  call     void Microsoft.Crm.Tools.Admin.GrantCrmDatabaseAccessAction::GrantServiceAccountAccess(valuetype [mscorlib]System.Guid organizationId, string sqlServerMachineName, class [System]System.Uri reportingUrl)
0x10f5e  ret
```
