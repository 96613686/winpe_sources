# Microsoft.Crm.Tools.Admin.InstallPrerequisiteSchemaUpdatesAction::Do

- ea: `0x10240`
- end: `0x1029f`
- name: `Microsoft.Crm.Tools.Admin.InstallPrerequisiteSchemaUpdatesAction::Do`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x84f0`
- `0x8630`
- `0x10240`

## string_xrefs

- `0x10275`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\BusinessConfiguration.cs`
- `0x1025f`: `if not exists (select 1 from sys.objects where object_id = object_id(N'CascadeOperation') and type in (N'U'))\n	create table [dbo].[CascadeOperation](\n		[CascadeLinkType] [int] NOT NULL,\n		[IsDeleteEntitySchema] [bit] default 0,\n		[HasExtraConditions] [bit] default 0,\n		[ReferencedEntityObjectTypeCode] [int] NOT NULL,\n		[ReferencingEntityObjectTypeCode] [int] NOT NULL,\n		[ReferencingAttributeColumnNumber] [int] NOT NULL,\n		[CascadeStatement] nvarchar(max),\n		primary key clustere`

## pseudocode

```c

```

## disassembly

```asm
0x10240  ldarg.1
0x10241  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0x10246  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x1024b  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0x10250  ldc.i4.0
0x10251  ldc.i4.0
0x10252  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x10257  stloc.0
0x10258  ldloc.0
0x10259  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1025e  ldloc.0
0x1025f  ldstr    aIfNotExistsSel// "if not exists (select 1 from sys.object"...
0x10264  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x10269  stloc.1
0x1026a  ldloc.1
0x1026b  ldc.i4   0xAF1
0x10270  ldstr    aDo// "Do"
0x10275  ldstr    aDDbsShDccm2110_8// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x1027a  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x1027f  pop
0x10280  leave.s  loc_1028C
0x10282  ldloc.1
0x10283  brfalse.s loc_1028B
0x10285  ldloc.1
0x10286  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1028b  endfinally
0x1028c  ldloc.0
0x1028d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0x10292  leave.s  loc_1029E
0x10294  ldloc.0
0x10295  brfalse.s loc_1029D
0x10297  ldloc.0
0x10298  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1029d  endfinally
0x1029e  ret
```
