# Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::Execute

- ea: `0x45d0`
- end: `0x46aa`
- name: `Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::Execute`
- size: `218`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x37e0`
- `0x165c0`
- `0x17500`

## callees

- `0x2650`
- `0x27d0`
- `0x4590`
- `0x45b0`
- `0x45d0`
- `0x46b0`
- `0x4710`

## pseudocode

```c

```

## disassembly

```asm
0x45d0  ldc.i4.1
0x45d1  stloc.0
0x45d2  ldarg.0
0x45d3  ldfld    int32 Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_retrySkipCount
0x45d8  brtrue.s loc_4629
0x45da  ldarg.0
0x45db  ldarg.0
0x45dc  ldfld    int32 Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_attemptCount
0x45e1  ldc.i4.1
0x45e2  add
0x45e3  stfld    int32 Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_attemptCount
0x45e8  ldarg.0
0x45e9  callvirt instance void Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::InternalExecute()
0x45ee  ldarg.0
0x45ef  ldfld    int32 Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_attemptCount
0x45f4  ldc.i4.1
0x45f5  ble.s    loc_4625
0x45f7  ldarg.1
0x45f8  ldc.i4.4
0x45f9  ldc.i4   0x40004405
0x45fe  conv.i8
0x45ff  ldc.i4.2
0x4600  newarr   [mscorlib]System.Object
0x4605  dup
0x4606  ldc.i4.0
0x4607  call     string [mscorlib]System.Environment::get_MachineName()
0x460c  stelem.ref
0x460d  dup
0x460e  ldc.i4.1
0x460f  ldarg.0
0x4610  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::get_Configuration()
0x4615  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x461a  box      [mscorlib]System.Guid
0x461f  stelem.ref
0x4620  callvirt instance void Microsoft.Crm.Asynchronous.AsyncManagerBase::LogEvent(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventId, object[] parameters)
0x4625  ldc.i4.0
0x4626  stloc.0
0x4627  br.s     loc_4639
0x4629  ldarg.0
0x462a  ldarg.0
0x462b  ldfld    int32 Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_retrySkipCount
0x4630  ldc.i4.1
0x4631  sub
0x4632  stfld    int32 Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::_retrySkipCount
0x4637  ldc.i4.2
0x4638  stloc.0
0x4639  leave.s  loc_46A8
0x463b  stloc.1
0x463c  ldloc.1
0x463d  isinst   [System.Data]System.Data.SqlClient.SqlException
0x4642  ldloc.1
0x4643  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x4648  stloc.2
0x4649  brtrue.s loc_4652
0x464b  ldloc.2
0x464c  brtrue.s loc_4652
0x464e  ldc.i4.1
0x464f  stloc.0
0x4650  br.s     loc_469E
0x4652  ldarg.1
0x4653  callvirt instance bool Microsoft.Crm.Asynchronous.AsyncManagerBase::get_ShuttingDown()
0x4658  brfalse.s loc_4695
0x465a  ldarg.1
0x465b  ldc.i4.1
0x465c  ldc.i4   0xC0004409
0x4661  conv.u8
0x4662  ldc.i4.3
0x4663  newarr   [mscorlib]System.Object
0x4668  dup
0x4669  ldc.i4.0
0x466a  call     string [mscorlib]System.Environment::get_MachineName()
0x466f  stelem.ref
0x4670  dup
0x4671  ldc.i4.1
0x4672  ldarg.0
0x4673  callvirt instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::get_Configuration()
0x4678  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x467d  box      [mscorlib]System.Guid
0x4682  stelem.ref
0x4683  dup
0x4684  ldc.i4.2
0x4685  ldloc.1
0x4686  callvirt instance string [mscorlib]System.Object::ToString()
0x468b  stelem.ref
0x468c  callvirt instance void Microsoft.Crm.Asynchronous.AsyncManagerBase::LogEvent(valuetype [System]System.Diagnostics.EventLogEntryType eventType, int64 eventId, object[] parameters)
0x4691  ldc.i4.1
0x4692  stloc.0
0x4693  br.s     loc_469E
0x4695  ldarg.0
0x4696  ldarg.1
0x4697  ldloc.1
0x4698  call     instance valuetype CommandResult Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::CalculateRetryOrFailure(class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase queueManager, class [mscorlib]System.Exception e)
0x469d  stloc.0
0x469e  ldarg.0
0x469f  ldloc.0
0x46a0  ldloc.1
0x46a1  call     instance void Microsoft.Crm.Asynchronous.QueuedDatabaseCommand::LogDatabaseCommandExceptions(valuetype CommandResult result, class [mscorlib]System.Exception e)
0x46a6  leave.s  loc_46A8
0x46a8  ldloc.0
0x46a9  ret
```
