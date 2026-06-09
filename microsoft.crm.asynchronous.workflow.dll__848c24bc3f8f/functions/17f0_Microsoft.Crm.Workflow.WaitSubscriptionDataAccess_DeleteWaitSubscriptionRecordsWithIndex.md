# Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::DeleteWaitSubscriptionRecordsWithIndex

- ea: `0x17f0`
- end: `0x1829`
- name: `Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::DeleteWaitSubscriptionRecordsWithIndex`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1760`

## string_xrefs

- `0x17f1`: `delete WorkflowWaitSubscriptionBase from WorkflowWaitSubscriptionBase with(index(ndx_CascadeRelationship_Asyncoperation_workflowwaitsubscription)) where AsyncOperationId=@workflowId`

## pseudocode

```c

```

## disassembly

```asm
0x17f0  ldarg.2
0x17f1  ldstr    aDeleteWorkflow// "delete WorkflowWaitSubscriptionBase fro"...
0x17f6  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x17fb  ldarg.2
0x17fc  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1801  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1806  ldstr    aWorkflowid// "@workflowId"
0x180b  ldarg.1
0x180c  box      [mscorlib]System.Guid
0x1811  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1816  pop
0x1817  ldarg.0
0x1818  ldarg.2
0x1819  ldloca.s 0
0x181b  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1821  ldloc.0
0x1822  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x1827  pop
0x1828  ret
```
