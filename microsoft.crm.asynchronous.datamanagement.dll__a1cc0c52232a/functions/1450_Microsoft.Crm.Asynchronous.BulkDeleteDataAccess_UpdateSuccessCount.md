# Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::UpdateSuccessCount

- ea: `0x1450`
- end: `0x148a`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::UpdateSuccessCount`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1e80`
- `0x2ea0`

## string_xrefs

- `0x1450`: `UPDATE BulkDeleteOperationBase SET SuccessCount=SuccessCount + 1 WHERE AsyncOperationId = @asyncOperationId`

## pseudocode

```c

```

## disassembly

```asm
0x1450  ldstr    aUpdateBulkdele// "UPDATE BulkDeleteOperationBase SET Succ"...
0x1455  ldc.i4.1
0x1456  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x145b  stloc.0
0x145c  ldloc.0
0x145d  ldstr    aAsyncoperation// "@asyncOperationId"
0x1462  ldarg.1
0x1463  box      [mscorlib]System.Guid
0x1468  ldloca.s 1
0x146a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1470  ldloc.1
0x1471  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x1476  ldarg.0
0x1477  ldloc.0
0x1478  ldarg.0
0x1479  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x147e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x1483  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, valuetype [mscorlib]System.Guid)
0x1488  pop
0x1489  ret
```
