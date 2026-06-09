# Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStateDataAccess::PostponeOrPreponeUpdateKnowledgeArticleStatesJob

- ea: `0xb160`
- end: `0xb212`
- name: `Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStateDataAccess::PostponeOrPreponeUpdateKnowledgeArticleStatesJob`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0xa7b0`

## callees

- `0xb160`

## string_xrefs

- `0xb177`: `update AsyncOperationBase\n				set\n					PostponeUntil = `
- `0xb17d`: `,ModifiedOn = @modifiedOn,\n					ModifiedBy = CreatedBy\n				where\n					AsyncOperationId = @id`
- `0xb1ec`: `Update Knowledge Article States handler's postponeuntil changed to {0}.`

## pseudocode

```c

```

## disassembly

```asm
0xb160  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xb165  stloc.0
0xb166  ldarg.3
0xb167  brtrue.s loc_B170
0xb169  ldstr    aCaseWhenCoales// "case when coalesce(PostponeUntil, @post"...
0xb16e  br.s     loc_B175
0xb170  ldstr    aPostponeuntil_0// "@postPoneUntil"
0xb175  stloc.1
0xb176  ldloc.0
0xb177  ldstr    aUpdateAsyncope_1// "update AsyncOperationBase\r\n\t\t\t\tse"...
0xb17c  ldloc.1
0xb17d  ldstr    aModifiedonModi_2// ",ModifiedOn = @modifiedOn,\r\n\t\t\t\t"...
0xb182  call     string [mscorlib]System.String::Concat(string, string, string)
0xb187  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0xb18c  ldloc.0
0xb18d  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0xb192  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0xb197  dup
0xb198  ldstr    aPostponeuntil_0// "@postPoneUntil"
0xb19d  ldarg.2
0xb19e  box      [mscorlib]System.DateTime
0xb1a3  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xb1a8  pop
0xb1a9  dup
0xb1aa  ldstr    aId// "@id"
0xb1af  ldarg.1
0xb1b0  box      [mscorlib]System.Guid
0xb1b5  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xb1ba  pop
0xb1bb  ldstr    aModifiedon_1// "@modifiedOn"
0xb1c0  ldarg.0
0xb1c1  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0xb1c6  box      [mscorlib]System.DateTime
0xb1cb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0xb1d0  pop
0xb1d1  ldarg.0
0xb1d2  ldloc.0
0xb1d3  ldc.i4.1
0xb1d4  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xb1d9  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0xb1de  pop
0xb1df  ldarg.0
0xb1e0  ldfld    class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.UpdateKnowledgeArticleStateDataAccess::_orgConfig
0xb1e5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xb1ea  ldc.i4.s 0x15
0xb1ec  ldstr    aUpdateKnowledg// "Update Knowledge Article States handler"...
0xb1f1  ldc.i4.1
0xb1f2  newarr   [mscorlib]System.Object
0xb1f7  dup
0xb1f8  ldc.i4.0
0xb1f9  ldarg.2
0xb1fa  box      [mscorlib]System.DateTime
0xb1ff  stelem.ref
0xb200  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb205  leave.s  loc_B211
0xb207  ldloc.0
0xb208  brfalse.s loc_B210
0xb20a  ldloc.0
0xb20b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb210  endfinally
0xb211  ret
```
