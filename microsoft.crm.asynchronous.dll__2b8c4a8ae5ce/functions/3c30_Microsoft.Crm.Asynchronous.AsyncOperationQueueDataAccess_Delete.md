# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::Delete

- ea: `0x3c30`
- end: `0x3cbf`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::Delete`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x16960`

## callees

- `0x2730`
- `0x2790`
- `0x3c30`
- `0xd5a0`
- `0xd7c0`

## string_xrefs

- `0x3c30`: `delete AsyncOperationBase Where AsyncOperationId = @id;`
- `0x3c83`: `{0}-{1}: Operation {2} could not be deleted. Exception: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x3c30  ldstr    aDeleteAsyncope// "delete AsyncOperationBase Where AsyncOp"...
0x3c35  ldc.i4.1
0x3c36  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x3c3b  stloc.0
0x3c3c  ldloc.0
0x3c3d  ldstr    aId// "@id"
0x3c42  ldarg.1
0x3c43  box      [mscorlib]System.Guid
0x3c48  ldloca.s 1
0x3c4a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3c50  ldloc.1
0x3c51  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x3c56  ldarg.0
0x3c57  ldloc.0
0x3c58  ldloca.s 1
0x3c5a  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3c60  ldloc.1
0x3c61  ldarg.0
0x3c62  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x3c67  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x3c6c  call     instance int32 Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteNonQuery(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo command, valuetype [mscorlib]System.Nullable`1<int32> expectedAffectedRecords, valuetype [mscorlib]System.Guid inputOrganizationId)
0x3c71  pop
0x3c72  leave.s  loc_3CBE
0x3c74  stloc.2
0x3c75  ldloc.2
0x3c76  ldarg.0
0x3c77  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x3c7c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x3c81  ldc.i4.s 0x15
0x3c83  ldstr    a01Operation2Co// "{0}-{1}: Operation {2} could not be del"...
0x3c88  ldc.i4.4
0x3c89  newarr   [mscorlib]System.Object
0x3c8e  dup
0x3c8f  ldc.i4.0
0x3c90  ldarg.0
0x3c91  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x3c96  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x3c9b  stelem.ref
0x3c9c  dup
0x3c9d  ldc.i4.1
0x3c9e  ldarg.0
0x3c9f  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x3ca4  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x3ca9  stelem.ref
0x3caa  dup
0x3cab  ldc.i4.2
0x3cac  ldarg.1
0x3cad  box      [mscorlib]System.Guid
0x3cb2  stelem.ref
0x3cb3  dup
0x3cb4  ldc.i4.3
0x3cb5  ldloc.2
0x3cb6  stelem.ref
0x3cb7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3cbc  rethrow
0x3cbe  ret
```
