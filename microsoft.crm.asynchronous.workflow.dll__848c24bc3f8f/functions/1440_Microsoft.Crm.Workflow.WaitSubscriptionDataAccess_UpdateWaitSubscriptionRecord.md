# Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::UpdateWaitSubscriptionRecord

- ea: `0x1440`
- end: `0x14f0`
- name: `Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::UpdateWaitSubscriptionRecord`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1390`

## callees

- `0x1440`

## string_xrefs

- `0x1447`: `update WorkflowWaitSubscriptionBase\n						set WaitOnAttributeList = @waitOnAttributeList\n						where EntityId = @entityId and \n						EntityName = @entityName and \n						AsyncOperationId = @asyncOperationId`
- `0x14b8`: `Workflow {0} subscribed for updates of entity instance ({1},{2}) on attributes {3}.`

## pseudocode

```c

```

## disassembly

```asm
0x1440  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x1445  stloc.0
0x1446  ldloc.0
0x1447  ldstr    aUpdateWorkflow// "update WorkflowWaitSubscriptionBase\r\n"...
0x144c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1451  ldloc.0
0x1452  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1457  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x145c  dup
0x145d  ldstr    aWaitonattribut// "@waitOnAttributeList"
0x1462  ldarg.s  4
0x1464  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1469  pop
0x146a  dup
0x146b  ldstr    aEntityid// "@entityId"
0x1470  ldarg.3
0x1471  box      [mscorlib]System.Guid
0x1476  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x147b  pop
0x147c  dup
0x147d  ldstr    aEntityname_0// "@entityName"
0x1482  ldarg.2
0x1483  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1488  pop
0x1489  ldstr    aAsyncoperation_0// "@asyncOperationId"
0x148e  ldarg.1
0x148f  box      [mscorlib]System.Guid
0x1494  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1499  pop
0x149a  ldarg.0
0x149b  ldloc.0
0x149c  ldloca.s 1
0x149e  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x14a4  ldloc.1
0x14a5  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x14aa  pop
0x14ab  ldarg.0
0x14ac  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x14b1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x14b6  ldc.i4.s 0x1E
0x14b8  ldstr    aWorkflow0Subsc// "Workflow {0} subscribed for updates of "...
0x14bd  ldc.i4.4
0x14be  newarr   [mscorlib]System.Object
0x14c3  dup
0x14c4  ldc.i4.0
0x14c5  ldarg.1
0x14c6  box      [mscorlib]System.Guid
0x14cb  stelem.ref
0x14cc  dup
0x14cd  ldc.i4.1
0x14ce  ldarg.2
0x14cf  stelem.ref
0x14d0  dup
0x14d1  ldc.i4.2
0x14d2  ldarg.3
0x14d3  box      [mscorlib]System.Guid
0x14d8  stelem.ref
0x14d9  dup
0x14da  ldc.i4.3
0x14db  ldarg.s  4
0x14dd  stelem.ref
0x14de  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x14e3  leave.s  loc_14EF
0x14e5  ldloc.0
0x14e6  brfalse.s loc_14EE
0x14e8  ldloc.0
0x14e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14ee  endfinally
0x14ef  ret
```
