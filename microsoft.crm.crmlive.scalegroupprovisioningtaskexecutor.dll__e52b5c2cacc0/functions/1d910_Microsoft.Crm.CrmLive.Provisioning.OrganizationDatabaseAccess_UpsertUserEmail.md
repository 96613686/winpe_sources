# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpsertUserEmail

- ea: `0x1d910`
- end: `0x1dac5`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpsertUserEmail`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1d810`

## callees

- `0x1d910`

## string_xrefs

- `0x1d965`: `DELETE FROM EmailSearchBase WHERE\n											ParentObjectId = @parentObjectId AND EmailColumnNumber = 15`
- `0x1d9e0`: `UPDATE EmailSearchBase\n											SET EmailAddress=@emailAddress\n											WHERE\n											ParentObjectId = @parentObjectId AND EmailColumnNumber = 15`

## pseudocode

```c

```

## disassembly

```asm
0x1d910  ldarg.1
0x1d911  box      [mscorlib]System.Guid
0x1d916  ldstr    aOrgid// "orgId"
0x1d91b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1d920  ldarg.1
0x1d921  ldstr    aOrgid// "orgId"
0x1d926  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1d92b  ldarg.2
0x1d92c  box      [mscorlib]System.Guid
0x1d931  ldstr    aSystemuserid_2// "systemUserId"
0x1d936  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1d93b  ldarg.2
0x1d93c  ldstr    aSystemuserid_2// "systemUserId"
0x1d941  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1d946  ldarg.0
0x1d947  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d94c  brfalse.s loc_1D9AB
0x1d94e  ldarg.1
0x1d94f  ldc.i4.0
0x1d950  ldc.i4.0
0x1d951  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1d956  stloc.0
0x1d957  ldloc.0
0x1d958  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1d95d  ldloc.0
0x1d95e  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1d963  stloc.1
0x1d964  ldloc.1
0x1d965  ldstr    aDeleteFromEmai// "DELETE FROM EmailSearchBase WHERE\r\n\t"...
0x1d96a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1d96f  ldloc.1
0x1d970  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1d975  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1d97a  ldstr    aParentobjectid// "parentObjectId"
0x1d97f  ldarg.2
0x1d980  box      [mscorlib]System.Guid
0x1d985  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1d98a  pop
0x1d98b  ldloc.1
0x1d98c  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x1d991  pop
0x1d992  leave    loc_1DAC4
0x1d997  ldloc.1
0x1d998  brfalse.s loc_1D9A0
0x1d99a  ldloc.1
0x1d99b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d9a0  endfinally
0x1d9a1  ldloc.0
0x1d9a2  brfalse.s loc_1D9AA
0x1d9a4  ldloc.0
0x1d9a5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d9aa  endfinally
0x1d9ab  ldarg.0
0x1d9ac  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1d9b1  ldc.i4.s 0x64
0x1d9b3  bgt.s    loc_1D9B8
0x1d9b5  ldarg.0
0x1d9b6  br.s     loc_1D9C1
0x1d9b8  ldarg.0
0x1d9b9  ldc.i4.0
0x1d9ba  ldc.i4.s 0x64
0x1d9bc  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1d9c1  stloc.2
0x1d9c2  ldc.i4.0
0x1d9c3  stloc.3
0x1d9c4  ldarg.1
0x1d9c5  ldc.i4.0
0x1d9c6  ldc.i4.0
0x1d9c7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1d9cc  stloc.s  4
0x1d9ce  ldloc.s  4
0x1d9d0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1d9d5  ldloc.s  4
0x1d9d7  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1d9dc  stloc.s  5
0x1d9de  ldloc.s  5
0x1d9e0  ldstr    aUpdateEmailsea// "UPDATE EmailSearchBase\r\n\t\t\t\t\t\t"...
0x1d9e5  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1d9ea  ldloc.s  5
0x1d9ec  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1d9f1  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1d9f6  dup
0x1d9f7  ldstr    aEmailaddress// "emailAddress"
0x1d9fc  ldloc.2
0x1d9fd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1da02  pop
0x1da03  ldstr    aParentobjectid// "parentObjectId"
0x1da08  ldarg.2
0x1da09  box      [mscorlib]System.Guid
0x1da0e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1da13  pop
0x1da14  ldloc.s  5
0x1da16  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x1da1b  stloc.3
0x1da1c  leave.s  loc_1DA36
0x1da1e  ldloc.s  5
0x1da20  brfalse.s loc_1DA29
0x1da22  ldloc.s  5
0x1da24  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1da29  endfinally
0x1da2a  ldloc.s  4
0x1da2c  brfalse.s loc_1DA35
0x1da2e  ldloc.s  4
0x1da30  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1da35  endfinally
0x1da36  ldloc.3
0x1da37  brtrue   loc_1DAC4
0x1da3c  ldarg.1
0x1da3d  ldc.i4.0
0x1da3e  ldc.i4.0
0x1da3f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1da44  stloc.s  6
0x1da46  ldloc.s  6
0x1da48  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1da4d  ldloc.s  6
0x1da4f  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1da54  stloc.s  7
0x1da56  ldloc.s  7
0x1da58  ldstr    aInsertIntoEmai// "INSERT INTO EmailSearchBase (EmailAddre"...
0x1da5d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1da62  ldloc.s  7
0x1da64  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1da69  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1da6e  dup
0x1da6f  ldstr    aEmailaddress// "emailAddress"
0x1da74  ldloc.2
0x1da75  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1da7a  pop
0x1da7b  dup
0x1da7c  ldstr    aParentobjectid// "parentObjectId"
0x1da81  ldarg.2
0x1da82  box      [mscorlib]System.Guid
0x1da87  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1da8c  pop
0x1da8d  ldstr    aEmailsearchid// "emailSearchId"
0x1da92  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x1da97  box      [mscorlib]System.Guid
0x1da9c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1daa1  pop
0x1daa2  ldloc.s  7
0x1daa4  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x1daa9  pop
0x1daaa  leave.s  loc_1DAC4
0x1daac  ldloc.s  7
0x1daae  brfalse.s loc_1DAB7
0x1dab0  ldloc.s  7
0x1dab2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1dab7  endfinally
0x1dab8  ldloc.s  6
0x1daba  brfalse.s loc_1DAC3
0x1dabc  ldloc.s  6
0x1dabe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1dac3  endfinally
0x1dac4  ret
```
