# Microsoft.Crm.Tools.Admin.SetOrganizationVersionAction::Do

- ea: `0xe040`
- end: `0xe0f0`
- name: `Microsoft.Crm.Tools.Admin.SetOrganizationVersionAction::Do`
- size: `176`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x84f0`
- `0x8630`
- `0x8a30`
- `0xe040`

## string_xrefs

- `0xe0c6`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\BusinessConfiguration.cs`
- `0xe094`: `UPDATE OrganizationBase SET InitialVersion = @initialVersion Where InitialVersion IS NULL`

## pseudocode

```c

```

## disassembly

```asm
0xe040  ldarg.1
0xe041  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xe046  stloc.0
0xe047  ldnull
0xe048  stloc.1
0xe049  ldloc.0
0xe04a  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ExistingDatabaseVersion()
0xe04f  ldnull
0xe050  call     bool [mscorlib]System.Version::op_Inequality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0xe055  brfalse.s loc_E060
0xe057  ldloc.0
0xe058  callvirt instance class [mscorlib]System.Version Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ExistingDatabaseVersion()
0xe05d  stloc.1
0xe05e  br.s     loc_E07A
0xe060  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0xe065  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0xe06a  call     class [System]System.Diagnostics.FileVersionInfo [System]System.Diagnostics.FileVersionInfo::GetVersionInfo(string)
0xe06f  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_FileVersion()
0xe074  newobj   instance void [mscorlib]System.Version::.ctor(string)
0xe079  stloc.1
0xe07a  ldloc.0
0xe07b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0xe080  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0xe085  ldc.i4.0
0xe086  ldc.i4.0
0xe087  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0xe08c  stloc.2
0xe08d  ldloc.2
0xe08e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xe093  ldloc.2
0xe094  ldstr    aUpdateOrganiza// "UPDATE OrganizationBase SET InitialVers"...
0xe099  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0xe09e  stloc.3
0xe09f  ldloc.3
0xe0a0  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xe0a5  isinst   [System.Data]System.Data.SqlClient.SqlParameterCollection
0xe0aa  ldstr    aInitialversion// "@initialVersion"
0xe0af  ldloc.1
0xe0b0  callvirt instance string [mscorlib]System.Object::ToString()
0xe0b5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xe0ba  pop
0xe0bb  ldloc.3
0xe0bc  ldc.i4   0x35E
0xe0c1  ldstr    aDo// "Do"
0xe0c6  ldstr    aDDbsShDccm2110_8// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0xe0cb  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0xe0d0  pop
0xe0d1  leave.s  loc_E0DD
0xe0d3  ldloc.3
0xe0d4  brfalse.s loc_E0DC
0xe0d6  ldloc.3
0xe0d7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe0dc  endfinally
0xe0dd  ldloc.2
0xe0de  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0xe0e3  leave.s  loc_E0EF
0xe0e5  ldloc.2
0xe0e6  brfalse.s loc_E0EE
0xe0e8  ldloc.2
0xe0e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe0ee  endfinally
0xe0ef  ret
```
