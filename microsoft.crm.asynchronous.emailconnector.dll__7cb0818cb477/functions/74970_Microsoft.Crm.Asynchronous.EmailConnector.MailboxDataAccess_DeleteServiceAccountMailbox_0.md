# Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::DeleteServiceAccountMailbox_0

- ea: `0x74970`
- end: `0x74aaa`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::DeleteServiceAccountMailbox_0`
- size: `314`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x718a0`

## callees

- `0x74970`

## string_xrefs

- `0x749cf`: `DELETE FROM MailboxBase `
- `0x749e7`: `and IsServiceAccount=@isServiceAccount`
- `0x749ff`: `@isServiceAccount`
- `0x74978`: `MailboxDataAccess.DeleteServiceAccountMailbox: Deleting Service Accounts for Mailbox: {0} StackTrace:{1}`
- `0x74a30`: `MailboxDataAccess.DeleteServiceAccountMailbox: Deleted {0} Service Account for Mailbox: {1} StackTrace:{2}`
- `0x74a69`: `MailboxDataAccess.DeleteServiceAccountMailbox: Cannot Delete Mailbox: {0} Invalid mailboxId StackTrace:{1}`

## pseudocode

```c

```

## disassembly

```asm
0x74970  ldarg.0
0x74971  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x74976  ldc.i4.s 0x3D
0x74978  ldstr    aMailboxdataacc_2// "MailboxDataAccess.DeleteServiceAccountM"...
0x7497d  ldc.i4.2
0x7497e  newarr   [mscorlib]System.Object
0x74983  dup
0x74984  ldc.i4.0
0x74985  ldarg.1
0x74986  stelem.ref
0x74987  dup
0x74988  ldc.i4.1
0x74989  call     string [mscorlib]System.Environment::get_StackTrace()
0x7498e  stelem.ref
0x7498f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x74994  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x74999  stloc.0
0x7499a  ldarg.1
0x7499b  ldloca.s 0
0x7499d  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x749a2  brfalse  loc_74A61
0x749a7  ldloc.0
0x749a8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x749ad  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x749b2  brfalse  loc_74A61
0x749b7  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x749bc  stloc.1
0x749bd  ldloc.1
0x749be  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x749c3  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x749c8  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x749cd  stloc.2
0x749ce  ldloc.2
0x749cf  ldstr    aDeleteFromMail// "DELETE FROM MailboxBase "
0x749d4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x749d9  pop
0x749da  ldloc.2
0x749db  ldstr    aWhereMailboxid// "WHERE MailboxId=@mailboxId"
0x749e0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x749e5  pop
0x749e6  ldloc.2
0x749e7  ldstr    aAndIsserviceac// "and IsServiceAccount=@isServiceAccount"
0x749ec  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x749f1  pop
0x749f2  dup
0x749f3  ldstr    aMailboxid_1// "@mailboxId"
0x749f8  ldarg.1
0x749f9  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x749fe  pop
0x749ff  ldstr    aIsserviceaccou_0// "@isServiceAccount"
0x74a04  ldc.i4.1
0x74a05  box      [mscorlib]System.Int32
0x74a0a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x74a0f  pop
0x74a10  ldloc.1
0x74a11  ldloc.2
0x74a12  callvirt instance string [mscorlib]System.Object::ToString()
0x74a17  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x74a1c  ldarg.0
0x74a1d  ldloc.1
0x74a1e  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand)
0x74a23  stloc.3
0x74a24  ldloc.3
0x74a25  ldc.i4.0
0x74a26  ble.s    loc_74A55
0x74a28  ldarg.0
0x74a29  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x74a2e  ldc.i4.s 0x3D
0x74a30  ldstr    aMailboxdataacc_3// "MailboxDataAccess.DeleteServiceAccountM"...
0x74a35  ldc.i4.3
0x74a36  newarr   [mscorlib]System.Object
0x74a3b  dup
0x74a3c  ldc.i4.0
0x74a3d  ldloc.3
0x74a3e  box      [mscorlib]System.Int32
0x74a43  stelem.ref
0x74a44  dup
0x74a45  ldc.i4.1
0x74a46  ldarg.1
0x74a47  stelem.ref
0x74a48  dup
0x74a49  ldc.i4.2
0x74a4a  call     string [mscorlib]System.Environment::get_StackTrace()
0x74a4f  stelem.ref
0x74a50  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x74a55  leave.s  loc_74AA9
0x74a57  ldloc.1
0x74a58  brfalse.s loc_74A60
0x74a5a  ldloc.1
0x74a5b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x74a60  endfinally
0x74a61  ldarg.0
0x74a62  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x74a67  ldc.i4.s 0x3D
0x74a69  ldstr    aMailboxdataacc_4// "MailboxDataAccess.DeleteServiceAccountM"...
0x74a6e  ldc.i4.2
0x74a6f  newarr   [mscorlib]System.Object
0x74a74  dup
0x74a75  ldc.i4.0
0x74a76  ldarg.1
0x74a77  stelem.ref
0x74a78  dup
0x74a79  ldc.i4.1
0x74a7a  call     string [mscorlib]System.Environment::get_StackTrace()
0x74a7f  stelem.ref
0x74a80  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x74a85  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x74a8a  ldstr    aInvalidMailbox// "Invalid mailbox id: {0} "
0x74a8f  ldc.i4.1
0x74a90  newarr   [mscorlib]System.Object
0x74a95  dup
0x74a96  ldc.i4.0
0x74a97  ldarg.1
0x74a98  stelem.ref
0x74a99  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x74a9e  ldstr    aMailboxid_2// "mailboxId"
0x74aa3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x74aa8  throw
0x74aa9  ret
```
