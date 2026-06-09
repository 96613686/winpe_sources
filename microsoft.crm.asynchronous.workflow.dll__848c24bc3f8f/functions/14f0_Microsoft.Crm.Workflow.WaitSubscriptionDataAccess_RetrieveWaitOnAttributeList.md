# Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::RetrieveWaitOnAttributeList

- ea: `0x14f0`
- end: `0x1571`
- name: `Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::RetrieveWaitOnAttributeList`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1390`

## callees

- `0x14f0`

## pseudocode

```c

```

## disassembly

```asm
0x14f0  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x14f5  stloc.0
0x14f6  ldloc.0
0x14f7  ldstr    aSelectWaitonat// "select WaitOnAttributeList from Workflo"...
0x14fc  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1501  ldloc.0
0x1502  ldc.i4.1
0x1503  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x1508  ldloc.0
0x1509  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x150e  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x1513  dup
0x1514  ldstr    aEntityid// "@entityId"
0x1519  ldarg.3
0x151a  box      [mscorlib]System.Guid
0x151f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1524  pop
0x1525  dup
0x1526  ldstr    aEntityname_0// "@entityName"
0x152b  ldarg.2
0x152c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1531  pop
0x1532  ldstr    aAsyncoperation_0// "@asyncOperationId"
0x1537  ldarg.1
0x1538  box      [mscorlib]System.Guid
0x153d  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1542  pop
0x1543  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1548  ldstr    a0// "{0}"
0x154d  ldc.i4.1
0x154e  newarr   [mscorlib]System.Object
0x1553  dup
0x1554  ldc.i4.0
0x1555  ldarg.0
0x1556  ldloc.0
0x1557  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand)
0x155c  stelem.ref
0x155d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1562  stloc.1
0x1563  leave.s  loc_156F
0x1565  ldloc.0
0x1566  brfalse.s loc_156E
0x1568  ldloc.0
0x1569  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x156e  endfinally
0x156f  ldloc.1
0x1570  ret
```
