# Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::DeleteServiceAccountMailbox

- ea: `0x74890`
- end: `0x7496e`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::DeleteServiceAccountMailbox`
- size: `222`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x7950`
- `0x789a0`

## callees

- `0x74890`

## string_xrefs

- `0x74898`: `MailboxDataAccess.DeleteServiceAccountMailbox: Deleting Service Accounts for Email Server Profile: {0} StackTrace:{1}`
- `0x748d1`: `DELETE FROM MailboxBase `
- `0x748e9`: `and IsServiceAccount=@isServiceAccount`
- `0x74906`: `@isServiceAccount`
- `0x74937`: `MailboxDataAccess.DeleteServiceAccountMailbox: Deleted {0} Service Account for Email Server Profile: {1} StackTrace:{2}`

## pseudocode

```c

```

## disassembly

```asm
0x74890  ldarg.0
0x74891  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x74896  ldc.i4.s 0x3D
0x74898  ldstr    aMailboxdataacc_0// "MailboxDataAccess.DeleteServiceAccountM"...
0x7489d  ldc.i4.2
0x7489e  newarr   [mscorlib]System.Object
0x748a3  dup
0x748a4  ldc.i4.0
0x748a5  ldarg.1
0x748a6  box      [mscorlib]System.Guid
0x748ab  stelem.ref
0x748ac  dup
0x748ad  ldc.i4.1
0x748ae  call     string [mscorlib]System.Environment::get_StackTrace()
0x748b3  stelem.ref
0x748b4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x748b9  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x748be  stloc.0
0x748bf  ldloc.0
0x748c0  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x748c5  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x748ca  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x748cf  stloc.1
0x748d0  ldloc.1
0x748d1  ldstr    aDeleteFromMail// "DELETE FROM MailboxBase "
0x748d6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x748db  pop
0x748dc  ldloc.1
0x748dd  ldstr    aWhereEmailserv// "WHERE EmailServerProfile=@emailServerPr"...
0x748e2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x748e7  pop
0x748e8  ldloc.1
0x748e9  ldstr    aAndIsserviceac// "and IsServiceAccount=@isServiceAccount"
0x748ee  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x748f3  pop
0x748f4  dup
0x748f5  ldstr    aEmailserverpro_5// "@emailServerProfileId"
0x748fa  ldarg.1
0x748fb  box      [mscorlib]System.Guid
0x74900  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x74905  pop
0x74906  ldstr    aIsserviceaccou_0// "@isServiceAccount"
0x7490b  ldc.i4.1
0x7490c  box      [mscorlib]System.Int32
0x74911  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x74916  pop
0x74917  ldloc.0
0x74918  ldloc.1
0x74919  callvirt instance string [mscorlib]System.Object::ToString()
0x7491e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x74923  ldarg.0
0x74924  ldloc.0
0x74925  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand)
0x7492a  stloc.2
0x7492b  ldloc.2
0x7492c  ldc.i4.0
0x7492d  ble.s    loc_74961
0x7492f  ldarg.0
0x74930  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x74935  ldc.i4.s 0x3D
0x74937  ldstr    aMailboxdataacc_1// "MailboxDataAccess.DeleteServiceAccountM"...
0x7493c  ldc.i4.3
0x7493d  newarr   [mscorlib]System.Object
0x74942  dup
0x74943  ldc.i4.0
0x74944  ldloc.2
0x74945  box      [mscorlib]System.Int32
0x7494a  stelem.ref
0x7494b  dup
0x7494c  ldc.i4.1
0x7494d  ldarg.1
0x7494e  box      [mscorlib]System.Guid
0x74953  stelem.ref
0x74954  dup
0x74955  ldc.i4.2
0x74956  call     string [mscorlib]System.Environment::get_StackTrace()
0x7495b  stelem.ref
0x7495c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x74961  leave.s  loc_7496D
0x74963  ldloc.0
0x74964  brfalse.s loc_7496C
0x74966  ldloc.0
0x74967  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7496c  endfinally
0x7496d  ret
```
