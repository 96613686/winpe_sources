# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::SetUserLicenseStateUsingSql

- ea: `0x1f140`
- end: `0x1f1d4`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::SetUserLicenseStateUsingSql`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1f140`

## string_xrefs

- `0x1f18d`: `issyncwithdirectory`
- `0x1f19f`: `UPDATE SystemUserBase SET IsLicensed=@islicensed, IsSyncWithDirectory=@issyncwithdirectory where SystemUserId=@systemuserid`
- `0x1f1ac`: `UPDATE SystemUserBase SET IsLicensed=@islicensed where SystemUserId=@systemuserid`

## pseudocode

```c

```

## disassembly

```asm
0x1f140  ldarg.1
0x1f141  ldc.i4.0
0x1f142  ldc.i4.0
0x1f143  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1f148  stloc.0
0x1f149  ldloc.0
0x1f14a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1f14f  ldloc.0
0x1f150  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1f155  stloc.1
0x1f156  ldloc.1
0x1f157  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1f15c  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1f161  stloc.2
0x1f162  ldloc.2
0x1f163  ldstr    aSystemuserid_0// "systemuserid"
0x1f168  ldarg.2
0x1f169  box      [mscorlib]System.Guid
0x1f16e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1f173  pop
0x1f174  ldloc.2
0x1f175  ldstr    aIslicensed// "islicensed"
0x1f17a  ldarg.3
0x1f17b  box      [mscorlib]System.Boolean
0x1f180  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1f185  pop
0x1f186  ldarg.3
0x1f187  ldarg.s  4
0x1f189  or
0x1f18a  brfalse.s loc_1F1AB
0x1f18c  ldloc.2
0x1f18d  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x1f192  ldc.i4.1
0x1f193  box      [mscorlib]System.Boolean
0x1f198  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1f19d  pop
0x1f19e  ldloc.1
0x1f19f  ldstr    aUpdateSystemus_1// "UPDATE SystemUserBase SET IsLicensed=@i"...
0x1f1a4  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1f1a9  br.s     loc_1F1B6
0x1f1ab  ldloc.1
0x1f1ac  ldstr    aUpdateSystemus_2// "UPDATE SystemUserBase SET IsLicensed=@i"...
0x1f1b1  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1f1b6  ldloc.1
0x1f1b7  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x1f1bc  pop
0x1f1bd  leave.s  loc_1F1D3
0x1f1bf  ldloc.1
0x1f1c0  brfalse.s loc_1F1C8
0x1f1c2  ldloc.1
0x1f1c3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f1c8  endfinally
0x1f1c9  ldloc.0
0x1f1ca  brfalse.s loc_1F1D2
0x1f1cc  ldloc.0
0x1f1cd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f1d2  endfinally
0x1f1d3  ret
```
