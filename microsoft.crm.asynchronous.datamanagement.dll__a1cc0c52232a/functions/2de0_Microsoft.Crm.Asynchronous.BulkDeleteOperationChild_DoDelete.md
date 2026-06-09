# Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::DoDelete

- ea: `0x2de0`
- end: `0x2e9c`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::DoDelete`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2c50`

## callees

- `0x15e0`
- `0x2de0`
- `0x2ea0`

## pseudocode

```c

```

## disassembly

```asm
0x2de0  br       loc_2E85
0x2de5  ldarg.0
0x2de6  ldfld    class Microsoft.Crm.Asynchronous.BulkDeleteDataAccess Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_bulkDeleteDataAccess
0x2deb  ldarg.0
0x2dec  ldfld    string Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_tempTableName
0x2df1  ldarg.0
0x2df2  ldfld    int32 Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_nextRow
0x2df7  ldarg.0
0x2df8  ldfld    int32 Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_lastRow
0x2dfd  callvirt instance class [mscorlib]System.Collections.Generic.List`1<object[]> Microsoft.Crm.Asynchronous.BulkDeleteDataAccess::GetRecordsIdsAndEntityNameForDeletionForIndependentEntities(string tableName, int32 nextRow, int32 lastRow)
0x2e02  stloc.0
0x2e03  ldloc.0
0x2e04  brfalse.s loc_2E73
0x2e06  ldloc.0
0x2e07  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<object[]>::get_Count()
0x2e0c  brfalse.s loc_2E73
0x2e0e  ldc.i4.0
0x2e0f  stloc.1
0x2e10  br.s     loc_2E6A
0x2e12  ldloc.1
0x2e13  ldc.i4.s 0xA
0x2e15  rem
0x2e16  brtrue.s loc_2E35
0x2e18  ldarg.1
0x2e19  callvirt instance valuetype [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerEarlyExitRequest [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::QueryForEarlyExitRequest()
0x2e1e  stloc.2
0x2e1f  ldloc.2
0x2e20  ldc.i4.1
0x2e21  beq.s    loc_2E29
0x2e23  ldloc.2
0x2e24  ldc.i4.2
0x2e25  beq.s    loc_2E2F
0x2e27  br.s     loc_2E35
0x2e29  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor()
0x2e2e  ret
0x2e2f  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncCanceledResult::.ctor()
0x2e34  ret
0x2e35  ldarg.0
0x2e36  ldloc.0
0x2e37  ldloc.1
0x2e38  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object[]>::get_Item(!!T0)
0x2e3d  ldc.i4.0
0x2e3e  ldelem.ref
0x2e3f  unbox.any [mscorlib]System.Guid
0x2e44  ldloc.0
0x2e45  ldloc.1
0x2e46  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object[]>::get_Item(!!T0)
0x2e4b  ldc.i4.1
0x2e4c  ldelem.ref
0x2e4d  castclass [mscorlib]System.String
0x2e52  ldarg.1
0x2e53  ldloc.0
0x2e54  ldloc.1
0x2e55  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<object[]>::get_Item(!!T0)
0x2e5a  ldc.i4.2
0x2e5b  ldelem.ref
0x2e5c  unbox.any [mscorlib]System.Int32
0x2e61  call     instance void Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::SWSDelete(valuetype [mscorlib]System.Guid recordId, string entityName, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent asyncEvent, int32 queryIndex)
0x2e66  ldloc.1
0x2e67  ldc.i4.1
0x2e68  add
0x2e69  stloc.1
0x2e6a  ldloc.1
0x2e6b  ldloc.0
0x2e6c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<object[]>::get_Count()
0x2e71  blt.s    loc_2E12
0x2e73  ldarg.0
0x2e74  ldarg.0
0x2e75  ldfld    int32 Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_nextRow
0x2e7a  ldc.i4   0x3E8
0x2e7f  add
0x2e80  stfld    int32 Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_nextRow
0x2e85  ldarg.0
0x2e86  ldfld    int32 Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_nextRow
0x2e8b  ldarg.0
0x2e8c  ldfld    int32 Microsoft.Crm.Asynchronous.BulkDeleteOperationChild::_lastRow
0x2e91  ble      loc_2DE5
0x2e96  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0x2e9b  ret
```
