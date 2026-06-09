# Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::RestartWaitingWorkflowInstances

- ea: `0x1830`
- end: `0x18c8`
- name: `Microsoft.Crm.Workflow.WaitSubscriptionDataAccess::RestartWaitingWorkflowInstances`
- size: `152`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x640`

## callees

- `0x1830`

## string_xrefs

- `0x1837`: `\nif exists (select * from WorkflowWaitSubscriptionBase (nolock) where IsModified = 1)\nbegin\nupdate AsyncOperationBase\nset\n	StateCode = @readyState,\n	StatusCode = @waitingStatus,\n	ModifiedOn = @modifiedOn,\n	ModifiedBy = CreatedBy\nwhere\n	StateCode = @suspendedState\nand RetryCount < @maxRetries\nand AsyncOperationId in (select AsyncOperationId from WorkflowWaitSubscriptionBase where IsModified = 1)\nend`
- `0x184d`: `@readyState`

## pseudocode

```c

```

## disassembly

```asm
0x1830  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x1835  stloc.0
0x1836  ldloc.0
0x1837  ldstr    aIfExistsSelect// "\r\nif exists (select * from WorkflowWa"...
0x183c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1841  ldloc.0
0x1842  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x1847  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x184c  dup
0x184d  ldstr    aReadystate// "@readyState"
0x1852  ldc.i4.0
0x1853  box      [mscorlib]System.Int32
0x1858  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x185d  pop
0x185e  dup
0x185f  ldstr    aSuspendedstate// "@suspendedState"
0x1864  ldc.i4.1
0x1865  box      [mscorlib]System.Int32
0x186a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x186f  pop
0x1870  dup
0x1871  ldstr    aWaitingstatus// "@waitingStatus"
0x1876  ldc.i4.0
0x1877  box      [mscorlib]System.Int32
0x187c  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1881  pop
0x1882  dup
0x1883  ldstr    aMaxretries// "@maxRetries"
0x1888  ldarg.1
0x1889  box      [mscorlib]System.Int32
0x188e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x1893  pop
0x1894  ldstr    aModifiedon// "@modifiedOn"
0x1899  ldarg.0
0x189a  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x189f  box      [mscorlib]System.DateTime
0x18a4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x18a9  pop
0x18aa  ldarg.0
0x18ab  ldloc.0
0x18ac  ldloca.s 1
0x18ae  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x18b4  ldloc.1
0x18b5  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::ExecuteSqlCommand(class [System.Data]System.Data.IDbCommand, valuetype [mscorlib]System.Nullable`1<int32>)
0x18ba  pop
0x18bb  leave.s  loc_18C7
0x18bd  ldloc.0
0x18be  brfalse.s loc_18C6
0x18c0  ldloc.0
0x18c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18c6  endfinally
0x18c7  ret
```
