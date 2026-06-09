# Microsoft.Crm.Workflow.WorkflowDataAccess::UpdateWorkflowInstanceStage

- ea: `0x2440`
- end: `0x24d3`
- name: `Microsoft.Crm.Workflow.WorkflowDataAccess::UpdateWorkflowInstanceStage`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2440`

## string_xrefs

- `0x2447`: `update AsyncOperationBase\nset\n	WorkflowStageName = @workflowStageName,\n	ModifiedOn = @modifiedOn,\n	ModifiedBy = CreatedBy\nwhere\n	AsyncOperationId = @id`
- `0x24b5`: `Workflow {0} has moved to stage '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x2440  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x2445  stloc.0
0x2446  ldloc.0
0x2447  ldstr    aUpdateAsyncope_0// "update AsyncOperationBase\r\nset\r\n\tW"...
0x244c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2451  ldloc.0
0x2452  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2457  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x245c  dup
0x245d  ldstr    aWorkflowstagen// "@workflowStageName"
0x2462  ldarg.2
0x2463  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2468  pop
0x2469  dup
0x246a  ldstr    aId// "@id"
0x246f  ldarg.1
0x2470  box      [mscorlib]System.Guid
0x2475  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x247a  pop
0x247b  ldstr    aModifiedon// "@modifiedOn"
0x2480  ldarg.0
0x2481  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x2486  box      [mscorlib]System.DateTime
0x248b  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2490  pop
0x2491  ldarg.0
0x2492  ldloc.0
0x2493  ldloca.s 1
0x2495  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x249b  ldloc.1
0x249c  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x24a1  pop
0x24a2  leave.s  loc_24AE
0x24a4  ldloc.0
0x24a5  brfalse.s loc_24AD
0x24a7  ldloc.0
0x24a8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24ad  endfinally
0x24ae  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x24b3  ldc.i4.s 0x1E
0x24b5  ldstr    aWorkflow0HasMo// "Workflow {0} has moved to stage '{1}'."
0x24ba  ldc.i4.2
0x24bb  newarr   [mscorlib]System.Object
0x24c0  dup
0x24c1  ldc.i4.0
0x24c2  ldarg.1
0x24c3  box      [mscorlib]System.Guid
0x24c8  stelem.ref
0x24c9  dup
0x24ca  ldc.i4.1
0x24cb  ldarg.2
0x24cc  stelem.ref
0x24cd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24d2  ret
```
