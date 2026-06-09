# Microsoft.Crm.Asynchronous.CleanupInactiveWorkflowAssembliesOperation::InternalExecute

- ea: `0x1ad0`
- end: `0x1b63`
- name: `Microsoft.Crm.Asynchronous.CleanupInactiveWorkflowAssembliesOperation::InternalExecute`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1ad0`

## string_xrefs

- `0x1b00`: `BEGIN\n							SET NOCOUNT ON\n							SET XACT_ABORT ON\n\n							DECLARE @RecordCountToDelete int = 1\n							DECLARE @ActivationsToDelete TABLE\n							(\n								WorkflowId UNIQUEIDENTIFIER\n							)\n\n							WHILE @RecordCountToDelete > 0\n								BEGIN\n									BEGIN tran\n										INSERT @ActivationsToDelete\n											SELECT TOP 5000 WorkflowId \n											FROM WorkflowBase\n											WHERE\n												Type = 2\n											AND (Category = 0 OR Category = 2 OR Categ`

## pseudocode

```c

```

## disassembly

```asm
0x1ad0  ldarg.1
0x1ad1  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0x1ad6  ldc.i4.s 0x20
0x1ad8  ceq
0x1ada  ldstr    aOperationTypeM_2// "Operation type must be 'CleanupInactive"...
0x1adf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1ae4  ldarg.1
0x1ae5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1aea  ldc.i4.0
0x1aeb  ldc.i4.0
0x1aec  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1af1  stloc.0
0x1af2  ldloc.0
0x1af3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1af8  ldloc.0
0x1af9  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x1afe  stloc.1
0x1aff  ldloc.1
0x1b00  ldstr    aBeginSetNocoun// "BEGIN\r\n\t\t\t\t\t\t\tSET NOCOUNT ON\r"...
0x1b05  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x1b0a  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x1b0f  ldstr    aCleanupinactiv// "CleanupInactiveWorkflowOperationTimeout"...
0x1b14  callvirt T0x2B000005
0x1b19  stloc.2
0x1b1a  ldloc.1
0x1b1b  ldloca.s 2
0x1b1d  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x1b22  brtrue.s loc_1B28
0x1b24  ldc.i4.s 0x78
0x1b26  br.s     loc_1B2F
0x1b28  ldloca.s 2
0x1b2a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x1b2f  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandTimeout(int32)
0x1b34  ldloc.1
0x1b35  ldc.i4.s 0x6F
0x1b37  ldstr    aInternalexecut// "InternalExecute"
0x1b3c  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x1b41  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x1b46  pop
0x1b47  leave.s  loc_1B5D
0x1b49  ldloc.1
0x1b4a  brfalse.s loc_1B52
0x1b4c  ldloc.1
0x1b4d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b52  endfinally
0x1b53  ldloc.0
0x1b54  brfalse.s loc_1B5C
0x1b56  ldloc.0
0x1b57  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b5c  endfinally
0x1b5d  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor()
0x1b62  ret
```
