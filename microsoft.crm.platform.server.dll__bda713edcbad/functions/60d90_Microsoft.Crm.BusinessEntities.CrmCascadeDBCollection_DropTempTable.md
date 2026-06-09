# Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::DropTempTable

- ea: `0x60d90`
- end: `0x60e80`
- name: `Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::DropTempTable`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x60b00`

## callees

- `0x60cf0`
- `0x60d90`
- `0x66af0`
- `0x66b00`

## string_xrefs

- `0x60e11`: `DropTempTable`
- `0x60e3e`: `ThreadAbort Exception in CascadeHelper.DropTempTable {0}`
- `0x60e63`: `Exception in CascadeHelper.DropTempTable: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x60d90  ldarg.0
0x60d91  call     instance bool Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::get_IsDeadLockVictim()
0x60d96  brfalse.s loc_60D99
0x60d98  ret
0x60d99  nop
0x60d9a  ldarg.0
0x60d9b  ldfld    bool Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::bIsTmpTblCreated
0x60da0  brfalse  loc_60E34
0x60da5  ldarg.0
0x60da6  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::context
0x60dab  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0x60db0  stloc.0
0x60db1  ldc.i4.1
0x60db2  ldloc.0
0x60db3  callvirt instance valuetype [System.Data]System.Data.ConnectionState [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_State()
0x60db8  beq.s    loc_60DBF
0x60dba  leave    loc_60E7F
0x60dbf  ldsfld   string [mscorlib]System.String::Empty
0x60dc4  stloc.1
0x60dc5  ldarg.0
0x60dc6  ldfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeActionType Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::opType
0x60dcb  ldc.i4.2
0x60dcc  bne.un.s loc_60DD6
0x60dce  ldstr    aDropTableCasca// "DROP TABLE #CascadeCollectAssign"
0x60dd3  stloc.1
0x60dd4  br.s     loc_60DED
0x60dd6  ldarg.0
0x60dd7  ldfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeActionType Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::opType
0x60ddc  ldc.i4.5
0x60ddd  bne.un.s loc_60DE7
0x60ddf  ldstr    aDropTableCasca_0// "DROP TABLE #CascadeCollectReparent"
0x60de4  stloc.1
0x60de5  br.s     loc_60DED
0x60de7  ldstr    aDropTableCasca_1// "DROP TABLE #CascadeCollect"
0x60dec  stloc.1
0x60ded  ldloc.0
0x60dee  ldloc.1
0x60def  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x60df4  stloc.2
0x60df5  ldloc.2
0x60df6  ldarg.0
0x60df7  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::context
0x60dfc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x60e01  callvirt instance class [System.Data]System.Data.IDbTransaction [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::get_SqlTrans()
0x60e06  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::SetTransaction(class [System.Data]System.Data.IDbCommand, class [System.Data]System.Data.IDbTransaction)
0x60e0b  ldloc.2
0x60e0c  ldc.i4   0x134
0x60e11  ldstr    aDroptemptable// "DropTempTable"
0x60e16  ldstr    aDA1SSrcManaged_14// "D:\\a\\1\\s\\src\\ManagedPlatform\\Serv"...
0x60e1b  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x60e20  pop
0x60e21  leave.s  loc_60E2D
0x60e23  ldloc.2
0x60e24  brfalse.s loc_60E2C
0x60e26  ldloc.2
0x60e27  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x60e2c  endfinally
0x60e2d  ldarg.0
0x60e2e  ldc.i4.0
0x60e2f  stfld    bool Microsoft.Crm.BusinessEntities.CrmCascadeDBCollection::bIsTmpTblCreated
0x60e34  leave.s  loc_60E7F
0x60e36  stloc.3
0x60e37  ldloc.3
0x60e38  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x60e3d  ldc.i4.6
0x60e3e  ldstr    aThreadabortExc// "ThreadAbort Exception in CascadeHelper."...
0x60e43  ldc.i4.1
0x60e44  newarr   [mscorlib]System.Object
0x60e49  dup
0x60e4a  ldc.i4.0
0x60e4b  ldloc.3
0x60e4c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x60e51  stelem.ref
0x60e52  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x60e57  rethrow
0x60e59  stloc.s  4
0x60e5b  ldloc.s  4
0x60e5d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x60e62  ldc.i4.6
0x60e63  ldstr    aExceptionInCas// "Exception in CascadeHelper.DropTempTabl"...
0x60e68  ldc.i4.1
0x60e69  newarr   [mscorlib]System.Object
0x60e6e  dup
0x60e6f  ldc.i4.0
0x60e70  ldloc.s  4
0x60e72  callvirt instance string [mscorlib]System.Exception::get_Message()
0x60e77  stelem.ref
0x60e78  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x60e7d  leave.s  loc_60E7F
0x60e7f  ret
```
