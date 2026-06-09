# Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::UpdateFailureCount

- ea: `0x1490`
- end: `0x14ca`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::UpdateFailureCount`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1fb0`
- `0x2fb0`

## string_xrefs

- `0x1490`: `UPDATE BulkDeleteOperationBase SET FailureCount=FailureCount + 1 WHERE AsyncOperationId = @asyncOperationId`

## pseudocode

```c

```

## disassembly

```asm
0x1490  ldstr    aUpdateBulkdele_0// "UPDATE BulkDeleteOperationBase SET Fail"...
0x1495  ldc.i4.1
0x1496  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x149b  stloc.0
0x149c  ldloc.0
0x149d  ldstr    aAsyncoperation// "@asyncOperationId"
0x14a2  ldarg.1
0x14a3  box      [mscorlib]System.Guid
0x14a8  ldloca.s 1
0x14aa  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x14b0  ldloc.1
0x14b1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x14b6  ldarg.0
0x14b7  ldloc.0
0x14b8  ldarg.0
0x14b9  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x14be  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x14c3  call     instance object [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteScalar(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, valuetype [mscorlib]System.Guid)
0x14c8  pop
0x14c9  ret
```
