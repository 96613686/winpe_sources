# Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::IsBulkDeleteOperationCompletedSuccessFully

- ea: `0x1540`
- end: `0x1584`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::IsBulkDeleteOperationCompletedSuccessFully`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1f350`

## string_xrefs

- `0x1540`: `SELECT FailureCount FROM BulkDeleteOperationBase WHERE AsyncOperationId = @asyncOperationId`

## pseudocode

```c

```

## disassembly

```asm
0x1540  ldstr    aSelectFailurec// "SELECT FailureCount FROM BulkDeleteOper"...
0x1545  ldc.i4.1
0x1546  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x154b  stloc.0
0x154c  ldloc.0
0x154d  ldstr    aAsyncoperation// "@asyncOperationId"
0x1552  ldarg.1
0x1553  box      [mscorlib]System.Guid
0x1558  ldloca.s 1
0x155a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1560  ldloc.1
0x1561  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x1566  ldarg.0
0x1567  ldloc.0
0x1568  ldarg.0
0x1569  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x156e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1573  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, valuetype [mscorlib]System.Guid)
0x1578  unbox.any [mscorlib]System.Int32
0x157d  ldc.i4.0
0x157e  cgt
0x1580  ldc.i4.0
0x1581  ceq
0x1583  ret
```
