# Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::Unsubscribe

- ea: `0x16e0`
- end: `0x1751`
- name: `Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::Unsubscribe`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x3560`

## callees

- `0x16e0`

## string_xrefs

- `0x16e7`: `delete from WorkflowWaitSubscriptionBase where WorkflowWaitSubscriptionId = @subscriptionId`

## pseudocode

```c

```

## disassembly

```asm
0x16e0  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x16e5  stloc.0
0x16e6  ldloc.0
0x16e7  ldstr    aDeleteFromWork// "delete from WorkflowWaitSubscriptionBas"...
0x16ec  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x16f1  ldloc.0
0x16f2  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x16f7  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x16fc  ldstr    aSubscriptionid// "@subscriptionId"
0x1701  ldarg.1
0x1702  box      [mscorlib]System.Guid
0x1707  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x170c  pop
0x170d  ldarg.0
0x170e  ldloc.0
0x170f  ldloca.s 1
0x1711  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1717  ldloc.1
0x1718  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x171d  pop
0x171e  leave.s  loc_172A
0x1720  ldloc.0
0x1721  brfalse.s loc_1729
0x1723  ldloc.0
0x1724  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1729  endfinally
0x172a  ldarg.0
0x172b  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x1730  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1735  ldc.i4.s 0x1E
0x1737  ldstr    aWorkflowUnsubs// "Workflow unsubscribed from subscription"...
0x173c  ldc.i4.1
0x173d  newarr   [mscorlib]System.Object
0x1742  dup
0x1743  ldc.i4.0
0x1744  ldarg.1
0x1745  box      [mscorlib]System.Guid
0x174a  stelem.ref
0x174b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1750  ret
```
