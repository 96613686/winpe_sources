# Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::CreateWaitSubscriptionRecord

- ea: `0x1580`
- end: `0x1688`
- name: `Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::CreateWaitSubscriptionRecord`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1390`

## callees

- `0x1580`

## string_xrefs

- `0x164e`: `Workflow {0} subscribed for updates of entity instance ({1},{2}) on attributes {3}.`

## pseudocode

```c

```

## disassembly

```asm
0x1580  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x1585  stloc.0
0x1586  ldloc.0
0x1587  ldstr    aIfNotExistsSel// "if not exists (select 1 from WorkflowWa"...
0x158c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1591  ldloc.0
0x1592  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1597  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x159c  dup
0x159d  ldstr    aWorkflowwaitsu// "@workflowWaitSubscriptionId"
0x15a2  ldarg.1
0x15a3  box      [mscorlib]System.Guid
0x15a8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x15ad  pop
0x15ae  dup
0x15af  ldstr    aAsyncoperation_0// "@asyncOperationId"
0x15b4  ldarg.2
0x15b5  box      [mscorlib]System.Guid
0x15ba  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x15bf  pop
0x15c0  dup
0x15c1  ldstr    aEntityname_0// "@entityName"
0x15c6  ldarg.s  4
0x15c8  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x15cd  pop
0x15ce  dup
0x15cf  ldstr    aEntityid// "@entityId"
0x15d4  ldarg.s  5
0x15d6  box      [mscorlib]System.Guid
0x15db  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x15e0  pop
0x15e1  dup
0x15e2  ldstr    aIsmodified// "@isModified"
0x15e7  ldc.i4.0
0x15e8  box      [mscorlib]System.Boolean
0x15ed  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x15f2  pop
0x15f3  dup
0x15f4  ldstr    aData// "@data"
0x15f9  ldarga.s 3
0x15fb  constrained. [mscorlib]System.Guid
0x1601  callvirt instance string [mscorlib]System.Object::ToString()
0x1606  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x160b  pop
0x160c  dup
0x160d  ldstr    aModifiedon// "@modifiedOn"
0x1612  ldarg.0
0x1613  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x1618  box      [mscorlib]System.DateTime
0x161d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1622  pop
0x1623  ldstr    aWaitonattribut// "@waitOnAttributeList"
0x1628  ldarg.s  6
0x162a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x162f  pop
0x1630  ldarg.0
0x1631  ldloc.0
0x1632  ldloca.s 1
0x1634  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x163a  ldloc.1
0x163b  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x1640  pop
0x1641  ldarg.0
0x1642  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x1647  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x164c  ldc.i4.s 0x1E
0x164e  ldstr    aWorkflow0Subsc// "Workflow {0} subscribed for updates of "...
0x1653  ldc.i4.4
0x1654  newarr   [mscorlib]System.Object
0x1659  dup
0x165a  ldc.i4.0
0x165b  ldarg.2
0x165c  box      [mscorlib]System.Guid
0x1661  stelem.ref
0x1662  dup
0x1663  ldc.i4.1
0x1664  ldarg.s  4
0x1666  stelem.ref
0x1667  dup
0x1668  ldc.i4.2
0x1669  ldarg.s  5
0x166b  box      [mscorlib]System.Guid
0x1670  stelem.ref
0x1671  dup
0x1672  ldc.i4.3
0x1673  ldarg.s  6
0x1675  stelem.ref
0x1676  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x167b  leave.s  loc_1687
0x167d  ldloc.0
0x167e  brfalse.s loc_1686
0x1680  ldloc.0
0x1681  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1686  endfinally
0x1687  ret
```
