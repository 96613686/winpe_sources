# Microsoft.Crm.Tools.Admin.MarkApplicationMetadataInvalidAction::Do

- ea: `0xe2d0`
- end: `0xe331`
- name: `Microsoft.Crm.Tools.Admin.MarkApplicationMetadataInvalidAction::Do`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x84f0`
- `0x8630`
- `0xe2d0`

## string_xrefs

- `0xe307`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\BusinessConfiguration.cs`
- `0xe2ee`: `\nIF OBJECT_ID('[SystemApplicationMetadataBase]','U') is not null\nBEGIN \n	update [SystemApplicationMetadataBase] \n	set [State]=2, [ModifiedOn]=GETUTCDATE()\n	where ([SystemApplicationMetadataId] = 'B7AD7D6F-AB4C-4261-AB8F-F8D61B3C1AB3')\n\n	update [SystemApplicationMetadataBase]\n	set [FormFactor]=1\n	where [FormFactor] is null\nEND\n\nIF OBJECT_ID('[UserApplicationMetadataBase]','U') is not null\nBEGIN \n	update [UserApplicationMetadataBase]\n	set [FormFactor]=1\n	where [Form`

## pseudocode

```c

```

## disassembly

```asm
0xe2d0  ldarg.1
0xe2d1  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xe2d6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0xe2db  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0xe2e0  ldc.i4.0
0xe2e1  ldc.i4.0
0xe2e2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xe2e7  stloc.0
0xe2e8  ldloc.0
0xe2e9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xe2ee  ldstr    aIfObjectIdSyst// "\r\nIF OBJECT_ID('[SystemApplicationMet"...
0xe2f3  stloc.1
0xe2f4  ldloc.0
0xe2f5  ldloc.1
0xe2f6  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0xe2fb  stloc.2
0xe2fc  ldloc.2
0xe2fd  ldc.i4   0x3FC
0xe302  ldstr    aDo// "Do"
0xe307  ldstr    aDDbsShDccm2110_8// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0xe30c  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xe311  pop
0xe312  leave.s  loc_E31E
0xe314  ldloc.2
0xe315  brfalse.s loc_E31D
0xe317  ldloc.2
0xe318  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe31d  endfinally
0xe31e  ldloc.0
0xe31f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0xe324  leave.s  loc_E330
0xe326  ldloc.0
0xe327  brfalse.s loc_E32F
0xe329  ldloc.0
0xe32a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe32f  endfinally
0xe330  ret
```
