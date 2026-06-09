# Microsoft.Crm.Workflow.WorkflowDataAccess::SaveWorkflowInstanceState

- ea: `0x22d0`
- end: `0x23c8`
- name: `Microsoft.Crm.Workflow.WorkflowDataAccess::SaveWorkflowInstanceState`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x22d0`

## string_xrefs

- `0x22d7`: `update AsyncOperationBase\nset\n	PostponeUntil = @postponeUntil,	\n	WorkflowState = @workflowState,\n	WorkflowIsBlocked = @workflowIsBlocked,\n	ModifiedOn = @modifiedOn,\n	ModifiedBy = CreatedBy\nwhere\n	AsyncOperationId = @id`

## pseudocode

```c

```

## disassembly

```asm
0x22d0  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x22d5  stloc.0
0x22d6  ldloc.0
0x22d7  ldstr    aUpdateAsyncope// "update AsyncOperationBase\r\nset\r\n\tP"...
0x22dc  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x22e1  ldloc.0
0x22e2  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x22e7  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x22ec  stloc.1
0x22ed  ldarg.s  4
0x22ef  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x22f4  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x22f9  brfalse.s loc_230E
0x22fb  ldloc.1
0x22fc  ldstr    aPostponeuntil// "@postponeUntil"
0x2301  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x2306  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x230b  pop
0x230c  br.s     loc_2321
0x230e  ldloc.1
0x230f  ldstr    aPostponeuntil// "@postponeUntil"
0x2314  ldarg.s  4
0x2316  box      [mscorlib]System.DateTime
0x231b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2320  pop
0x2321  ldloc.1
0x2322  ldstr    aWorkflowstate// "@workflowState"
0x2327  ldarg.2
0x2328  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x232d  pop
0x232e  ldloc.1
0x232f  ldstr    aWorkflowisbloc// "@workflowIsBlocked"
0x2334  ldarg.3
0x2335  box      [mscorlib]System.Boolean
0x233a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x233f  pop
0x2340  ldloc.1
0x2341  ldstr    aId// "@id"
0x2346  ldarg.1
0x2347  box      [mscorlib]System.Guid
0x234c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2351  pop
0x2352  ldloc.1
0x2353  ldstr    aModifiedon// "@modifiedOn"
0x2358  ldarg.0
0x2359  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x235e  box      [mscorlib]System.DateTime
0x2363  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2368  pop
0x2369  ldarg.0
0x236a  ldloc.0
0x236b  ldloca.s 2
0x236d  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x2373  ldloc.2
0x2374  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x2379  pop
0x237a  leave.s  loc_2386
0x237c  ldloc.0
0x237d  brfalse.s loc_2385
0x237f  ldloc.0
0x2380  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2385  endfinally
0x2386  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x238b  ldc.i4.s 0x1E
0x238d  ldstr    aWorkflow0HasBe// "Workflow {0} has been persisted; state "...
0x2392  ldc.i4.4
0x2393  newarr   [mscorlib]System.Object
0x2398  dup
0x2399  ldc.i4.0
0x239a  ldarg.1
0x239b  box      [mscorlib]System.Guid
0x23a0  stelem.ref
0x23a1  dup
0x23a2  ldc.i4.1
0x23a3  ldarg.2
0x23a4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x23a9  box      [mscorlib]System.Int32
0x23ae  stelem.ref
0x23af  dup
0x23b0  ldc.i4.2
0x23b1  ldarg.s  4
0x23b3  box      [mscorlib]System.DateTime
0x23b8  stelem.ref
0x23b9  dup
0x23ba  ldc.i4.3
0x23bb  ldarg.3
0x23bc  box      [mscorlib]System.Boolean
0x23c1  stelem.ref
0x23c2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x23c7  ret
```
