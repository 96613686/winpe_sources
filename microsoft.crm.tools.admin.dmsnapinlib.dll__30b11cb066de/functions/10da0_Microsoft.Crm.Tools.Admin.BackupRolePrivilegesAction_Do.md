# Microsoft.Crm.Tools.Admin.BackupRolePrivilegesAction::Do

- ea: `0x10da0`
- end: `0x10e01`
- name: `Microsoft.Crm.Tools.Admin.BackupRolePrivilegesAction::Do`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x84f0`
- `0x8630`
- `0x10da0`

## string_xrefs

- `0x10dd7`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\DatabaseConfiguration.cs`
- `0x10da6`: `IF EXISTS (SELECT * FROM sys.tables WHERE object_id = object_id(N'dbo.RoleTemplatePrivilegesOldBackup'))\nBEGIN\nDROP TABLE [dbo].[RoleTemplatePrivilegesOldBackup]\nEND\n\nCREATE TABLE [dbo].[RoleTemplatePrivilegesOldBackup]( [RoleTemplateId] [uniqueidentifier] NOT NULL, [PrivilegeId] [uniqueidentifier] NOT NULL, [IsBasic] [bit] NOT NULL,\n[IsLocal] [bit] NOT NULL, [IsDeep] [bit] NOT NULL, [IsGlobal] [bit] NOT NULL, [Upgrading] [bit] NOT NULL, [RoleTemplatePrivilegeId] [uniqueidentifier] N`

## pseudocode

```c

```

## disassembly

```asm
0x10da0  ldarg.1
0x10da1  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0x10da6  ldstr    aIfExistsSelect_2// "IF EXISTS (SELECT * FROM sys.tables WHE"...
0x10dab  stloc.0
0x10dac  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x10db1  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0x10db6  ldc.i4.0
0x10db7  ldc.i4.0
0x10db8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x10dbd  stloc.1
0x10dbe  ldloc.1
0x10dbf  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x10dc4  ldloc.1
0x10dc5  ldloc.0
0x10dc6  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x10dcb  stloc.2
0x10dcc  ldloc.2
0x10dcd  ldc.i4   0x277
0x10dd2  ldstr    aDo// "Do"
0x10dd7  ldstr    aDDbsShDccm2110_9// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x10ddc  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x10de1  pop
0x10de2  leave.s  loc_10DEE
0x10de4  ldloc.2
0x10de5  brfalse.s loc_10DED
0x10de7  ldloc.2
0x10de8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10ded  endfinally
0x10dee  ldloc.1
0x10def  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x10df4  leave.s  loc_10E00
0x10df6  ldloc.1
0x10df7  brfalse.s loc_10DFF
0x10df9  ldloc.1
0x10dfa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10dff  endfinally
0x10e00  ret
```
