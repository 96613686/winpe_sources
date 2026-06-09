# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateMailboxNames

- ea: `0x207d0`
- end: `0x208a2`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::UpdateMailboxNames`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1d810`

## callees

- `0x207d0`

## string_xrefs

- `0x2081d`: `update MailboxBase set Name=@name, RegardingObjectIdName=@name, EmailAddress=@useremail where RegardingObjectId = @regardingobjectid`
- `0x2087a`: `update MailboxBase set Name=@name, RegardingObjectIdName=@name where RegardingObjectId in (select QueueId from SystemUserBase where SystemUserId=@regardingobjectid)`

## pseudocode

```c

```

## disassembly

```asm
0x207d0  ldarg.0
0x207d1  ldc.i4.0
0x207d2  ldc.i4.0
0x207d3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x207d8  stloc.0
0x207d9  ldloc.0
0x207da  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x207df  ldloc.0
0x207e0  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x207e5  stloc.1
0x207e6  ldloc.1
0x207e7  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x207ec  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x207f1  dup
0x207f2  ldstr    aRegardingobjec// "regardingobjectid"
0x207f7  ldarg.1
0x207f8  box      [mscorlib]System.Guid
0x207fd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x20802  pop
0x20803  dup
0x20804  ldstr    aName_0// "name"
0x20809  ldarg.2
0x2080a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2080f  pop
0x20810  ldstr    aUseremail// "useremail"
0x20815  ldarg.3
0x20816  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2081b  pop
0x2081c  ldloc.1
0x2081d  ldstr    aUpdateMailboxb_1// "update MailboxBase set Name=@name, Rega"...
0x20822  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x20827  ldloc.1
0x20828  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x2082d  pop
0x2082e  leave.s  loc_2083A
0x20830  ldloc.1
0x20831  brfalse.s loc_20839
0x20833  ldloc.1
0x20834  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20839  endfinally
0x2083a  ldloc.0
0x2083b  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x20840  stloc.2
0x20841  ldloc.2
0x20842  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x20847  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x2084c  dup
0x2084d  ldstr    aRegardingobjec// "regardingobjectid"
0x20852  ldarg.1
0x20853  box      [mscorlib]System.Guid
0x20858  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2085d  pop
0x2085e  ldstr    aName_0// "name"
0x20863  ldstr    asc_4C552// "<"
0x20868  ldarg.2
0x20869  ldstr    asc_4C556// ">"
0x2086e  call     string [mscorlib]System.String::Concat(string, string, string)
0x20873  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x20878  pop
0x20879  ldloc.2
0x2087a  ldstr    aUpdateMailboxb_2// "update MailboxBase set Name=@name, Rega"...
0x2087f  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x20884  ldloc.2
0x20885  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x2088a  pop
0x2088b  leave.s  loc_208A1
0x2088d  ldloc.2
0x2088e  brfalse.s loc_20896
0x20890  ldloc.2
0x20891  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20896  endfinally
0x20897  ldloc.0
0x20898  brfalse.s loc_208A0
0x2089a  ldloc.0
0x2089b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x208a0  endfinally
0x208a1  ret
```
