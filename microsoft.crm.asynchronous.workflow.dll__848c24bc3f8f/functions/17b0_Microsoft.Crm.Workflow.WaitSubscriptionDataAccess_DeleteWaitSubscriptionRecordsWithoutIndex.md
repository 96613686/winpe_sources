# Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::DeleteWaitSubscriptionRecordsWithoutIndex

- ea: `0x17b0`
- end: `0x17e9`
- name: `Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::DeleteWaitSubscriptionRecordsWithoutIndex`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1760`

## string_xrefs

- `0x17b1`: `delete from WorkflowWaitSubscriptionBase where AsyncOperationId = @workflowId2`

## pseudocode

```c

```

## disassembly

```asm
0x17b0  ldarg.2
0x17b1  ldstr    aDeleteFromWork_0// "delete from WorkflowWaitSubscriptionBas"...
0x17b6  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x17bb  ldarg.2
0x17bc  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x17c1  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x17c6  ldstr    aWorkflowid2// "@workflowId2"
0x17cb  ldarg.1
0x17cc  box      [mscorlib]System.Guid
0x17d1  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x17d6  pop
0x17d7  ldarg.0
0x17d8  ldarg.2
0x17d9  ldloca.s 0
0x17db  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x17e1  ldloc.0
0x17e2  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x17e7  pop
0x17e8  ret
```
