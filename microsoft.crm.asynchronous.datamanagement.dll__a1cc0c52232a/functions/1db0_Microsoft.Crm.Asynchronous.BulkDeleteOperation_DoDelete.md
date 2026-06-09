# Microsoft.Crm.Asynchronous.BulkDeleteOperation::DoDelete

- ea: `0x1db0`
- end: `0x1e77`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::DoDelete`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1f350`

## callees

- `0x10d0`
- `0x11f0`
- `0x1db0`
- `0x1e80`
- `0x2150`
- `0x23d0`

## pseudocode

```c

```

## disassembly

```asm
0x1db0  ldc.i4.0
0x1db1  stloc.0
0x1db2  br       loc_1E60
0x1db7  ldarg.0
0x1db8  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_globalQueryExpList
0x1dbd  ldarg.0
0x1dbe  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_orderedQueryExpList
0x1dc3  ldloc.0
0x1dc4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::get_Item(!!T0)
0x1dc9  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::IndexOf(var<u1>)
0x1dce  stloc.1
0x1dcf  ldarg.0
0x1dd0  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x1dd5  ldarg.0
0x1dd6  ldfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperation::_tempDependentTableName
0x1ddb  ldloc.1
0x1ddc  ldloca.s 2
0x1dde  callvirt instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::GetRecordsIdsAndEntityNameForDeletion(string tableName, int32 queryIndex, [out] string& entityName)
0x1de3  stloc.3
0x1de4  ldloc.3
0x1de5  brfalse.s loc_1E1F
0x1de7  ldloc.3
0x1de8  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x1ded  brfalse.s loc_1E1F
0x1def  ldloc.2
0x1df0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1df5  brtrue.s loc_1E1F
0x1df7  ldc.i4.0
0x1df8  stloc.s  4
0x1dfa  br.s     loc_1E13
0x1dfc  ldarg.0
0x1dfd  ldloc.3
0x1dfe  ldloc.s  4
0x1e00  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Item(!!T0)
0x1e05  ldloc.2
0x1e06  ldarg.1
0x1e07  ldloc.1
0x1e08  call     instance void Microsoft.Crm.Asynchronous.BulkDeleteOperation::SWSDelete(valuetype [mscorlib]System.Guid recordId, string entityName, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, int32 queryIndex)
0x1e0d  ldloc.s  4
0x1e0f  ldc.i4.1
0x1e10  add
0x1e11  stloc.s  4
0x1e13  ldloc.s  4
0x1e15  ldloc.3
0x1e16  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x1e1b  blt.s    loc_1DFC
0x1e1d  br.s     loc_1E23
0x1e1f  ldloc.0
0x1e20  ldc.i4.1
0x1e21  add
0x1e22  stloc.0
0x1e23  ldarg.1
0x1e24  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::QueryForEarlyExitRequest()
0x1e29  stloc.s  5
0x1e2b  ldloc.s  5
0x1e2d  ldc.i4.1
0x1e2e  beq.s    loc_1E37
0x1e30  ldloc.s  5
0x1e32  ldc.i4.2
0x1e33  beq.s    loc_1E43
0x1e35  br.s     loc_1E60
0x1e37  ldarg.0
0x1e38  call     instance void Microsoft.Crm.Asynchronous.BulkDeleteOperation::PauseAllChildJobs()
0x1e3d  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor()
0x1e42  ret
0x1e43  ldarg.0
0x1e44  call     instance void Microsoft.Crm.Asynchronous.BulkDeleteOperation::CancelAllChildJobs()
0x1e49  ldarg.0
0x1e4a  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperation::_bulkDeleteDataAccess
0x1e4f  ldarg.0
0x1e50  ldfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperation::_tempDependentTableName
0x1e55  callvirt instance void Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::DeleteTempTable(string tableName)
0x1e5a  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult::.ctor()
0x1e5f  ret
0x1e60  ldloc.0
0x1e61  ldarg.0
0x1e62  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression> Microsoft.Crm.Asynchronous.BulkDeleteOperation::_orderedQueryExpList
0x1e67  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression>::get_Count()
0x1e6c  blt      loc_1DB7
0x1e71  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0x1e76  ret
```
