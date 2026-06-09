# Microsoft.Crm.Asynchronous.UpdateAsyncJobDataAccess::PostponeOrPrepone

- ea: `0x8d50`
- end: `0x8e0b`
- name: `Microsoft.Crm.Asynchronous.UpdateAsyncJobDataAccess::PostponeOrPrepone`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x8ea0`

## callees

- `0x8d50`

## string_xrefs

- `0x8d67`: `update AsyncOperationBase\nset\n	PostponeUntil = `
- `0x8d6d`: `,ModifiedOn = @modifiedOn,\n	ModifiedBy = CreatedBy\nwhere\n	AsyncOperationId = @id`

## pseudocode

```c

```

## disassembly

```asm
0x8d50  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x8d55  stloc.0
0x8d56  ldarg.3
0x8d57  brtrue.s loc_8D60
0x8d59  ldstr    aCaseWhenCoales// "case when coalesce(PostponeUntil, @post"...
0x8d5e  br.s     loc_8D65
0x8d60  ldstr    aPostponeuntil_0// "@postPoneUntil"
0x8d65  stloc.1
0x8d66  ldloc.0
0x8d67  ldstr    aUpdateAsyncope_0// "update AsyncOperationBase\r\nset\r\n\tP"...
0x8d6c  ldloc.1
0x8d6d  ldstr    aModifiedonModi_1// ",ModifiedOn = @modifiedOn,\r\n\tModifie"...
0x8d72  call     string [mscorlib]System.String::Concat(string, string, string)
0x8d77  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x8d7c  ldloc.0
0x8d7d  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x8d82  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x8d87  dup
0x8d88  ldstr    aPostponeuntil_0// "@postPoneUntil"
0x8d8d  ldarg.2
0x8d8e  box      [mscorlib]System.DateTime
0x8d93  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8d98  pop
0x8d99  dup
0x8d9a  ldstr    aId// "@id"
0x8d9f  ldarg.1
0x8da0  box      [mscorlib]System.Guid
0x8da5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8daa  pop
0x8dab  ldstr    aModifiedon_1// "@modifiedOn"
0x8db0  ldarg.0
0x8db1  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x8db6  box      [mscorlib]System.DateTime
0x8dbb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8dc0  pop
0x8dc1  ldarg.0
0x8dc2  ldloc.0
0x8dc3  ldc.i4.1
0x8dc4  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x8dc9  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x8dce  pop
0x8dcf  ldarg.0
0x8dd0  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.UpdateAsyncJobDataAccess::_orgConfig
0x8dd5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x8dda  ldc.i4.s 0x15
0x8ddc  ldstr    a1HandlerSPostp// "{1} handler's postponeuntil changed to "...
0x8de1  ldc.i4.2
0x8de2  newarr   [mscorlib]System.Object
0x8de7  dup
0x8de8  ldc.i4.0
0x8de9  ldarg.2
0x8dea  box      [mscorlib]System.DateTime
0x8def  stelem.ref
0x8df0  dup
0x8df1  ldc.i4.1
0x8df2  ldarg.0
0x8df3  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_Name()
0x8df8  stelem.ref
0x8df9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8dfe  leave.s  loc_8E0A
0x8e00  ldloc.0
0x8e01  brfalse.s loc_8E09
0x8e03  ldloc.0
0x8e04  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8e09  endfinally
0x8e0a  ret
```
