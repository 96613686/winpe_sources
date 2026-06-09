# Microsoft.Crm.Tools.Admin.CleanupOrphanedDataAction::CleanupOrphanedPBL

- ea: `0xdb40`
- end: `0xdba1`
- name: `Microsoft.Crm.Tools.Admin.CleanupOrphanedDataAction::CleanupOrphanedPBL`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0xdb30`

## callees

- `0x84f0`
- `0x8630`
- `0xdb40`

## string_xrefs

- `0xdb5e`: `\ndeclare OrphanedWorkflows cursor for\n( \n	(select W.WorkflowId from WorkflowBase W\n		Left Join MetadataSchema.Entity E on W.PrimaryEntity=E.ObjectTypeCode\n		where W.Category=2 and E.ObjectTypeCode is null)\n	);\n\n	declare @currentWorkflowID uniqueidentifier;\n	open OrphanedWorkflows;\n\n	fetch next from OrphanedWorkflows into @currentWorkflowID;\n	while @@FETCH_STATUS = 0\n	begin \n\n	--iterate through stored workflowIDs and delete as needed\n	delete from DependencyBase \n`
- `0xdb77`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\BusinessConfiguration.cs`

## pseudocode

```c

```

## disassembly

```asm
0xdb40  ldarg.1
0xdb41  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xdb46  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0xdb4b  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0xdb50  ldc.i4.0
0xdb51  ldc.i4.0
0xdb52  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xdb57  stloc.0
0xdb58  ldloc.0
0xdb59  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xdb5e  ldstr    aDeclareOrphane// "\r\ndeclare OrphanedWorkflows cursor fo"...
0xdb63  stloc.1
0xdb64  ldloc.0
0xdb65  ldloc.1
0xdb66  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0xdb6b  stloc.2
0xdb6c  ldloc.2
0xdb6d  ldc.i4   0x22C
0xdb72  ldstr    aCleanuporphane// "CleanupOrphanedPBL"
0xdb77  ldstr    aDDbsShDccm2110_8// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0xdb7c  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xdb81  pop
0xdb82  leave.s  loc_DB8E
0xdb84  ldloc.2
0xdb85  brfalse.s loc_DB8D
0xdb87  ldloc.2
0xdb88  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdb8d  endfinally
0xdb8e  ldloc.0
0xdb8f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0xdb94  leave.s  loc_DBA0
0xdb96  ldloc.0
0xdb97  brfalse.s loc_DB9F
0xdb99  ldloc.0
0xdb9a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xdb9f  endfinally
0xdba0  ret
```
