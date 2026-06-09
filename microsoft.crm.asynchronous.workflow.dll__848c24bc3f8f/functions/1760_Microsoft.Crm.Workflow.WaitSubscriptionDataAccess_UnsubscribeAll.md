# Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::UnsubscribeAll

- ea: `0x1760`
- end: `0x17ac`
- name: `Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::UnsubscribeAll`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1690`
- `0x35b0`

## callees

- `0x1760`
- `0x17b0`
- `0x17f0`

## pseudocode

```c

```

## disassembly

```asm
0x1760  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x1765  stloc.0
0x1766  ldarg.0
0x1767  ldarg.1
0x1768  ldloc.0
0x1769  call     instance void Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::DeleteWaitSubscriptionRecordsWithIndex(valuetype [mscorlib]System.Guid workflowInstanceId, class [System.Data]System.Data.IDbCommand command)
0x176e  leave.s  loc_1785
0x1770  pop
0x1771  ldarg.0
0x1772  ldarg.1
0x1773  ldloc.0
0x1774  call     instance void Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::DeleteWaitSubscriptionRecordsWithoutIndex(valuetype [mscorlib]System.Guid workflowInstanceId, class [System.Data]System.Data.IDbCommand command)
0x1779  leave.s  loc_1785
0x177b  ldloc.0
0x177c  brfalse.s loc_1784
0x177e  ldloc.0
0x177f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1784  endfinally
0x1785  ldarg.0
0x1786  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x178b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1790  ldc.i4.s 0x1E
0x1792  ldstr    aWorkflow0Unsub// "Workflow {0} unsubscribed from all subs"...
0x1797  ldc.i4.1
0x1798  newarr   [mscorlib]System.Object
0x179d  dup
0x179e  ldc.i4.0
0x179f  ldarg.1
0x17a0  box      [mscorlib]System.Guid
0x17a5  stelem.ref
0x17a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x17ab  ret
```
