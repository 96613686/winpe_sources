# Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::CleanStaleActionCards

- ea: `0x850`
- end: `0x976`
- name: `Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::CleanStaleActionCards`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x150`

## callees

- `0x850`

## string_xrefs

- `0x858`: `delete top ({0}) from [actioncardbase] where StartDate > '{1}'`
- `0x90c`: `Totally {0} records deleted from Action Cards table and time taken is {1}`

## pseudocode

```c

```

## disassembly

```asm
0x850  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x855  stloc.0
0x856  ldc.i4.0
0x857  stloc.1
0x858  ldstr    aDeleteTop0From// "delete top ({0}) from [actioncardbase] "...
0x85d  ldc.i4   0x186A0
0x862  box      [mscorlib]System.Int32
0x867  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x86c  stloc.3
0x86d  ldloca.s 3
0x86f  ldc.r8   8.0
0x878  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x87d  stloc.3
0x87e  ldloca.s 3
0x880  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x885  box      [mscorlib]System.DateTime
0x88a  call     string [mscorlib]System.String::Format(string, object, object)
0x88f  stloc.2
0x890  ldarg.0
0x891  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x896  ldc.i4.0
0x897  ldc.i4.0
0x898  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x89d  stloc.s  4
0x89f  ldloc.s  4
0x8a1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x8a6  ldloc.s  4
0x8a8  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x8ad  stloc.s  5
0x8af  ldloc.s  5
0x8b1  ldloc.2
0x8b2  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x8b7  ldloc.s  5
0x8b9  ldc.i4   0xFE
0x8be  ldstr    aCleanstaleacti// "CleanStaleActionCards"
0x8c3  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x8c8  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x8cd  stloc.1
0x8ce  leave.s  loc_8DC
0x8d0  ldloc.s  5
0x8d2  brfalse.s loc_8DB
0x8d4  ldloc.s  5
0x8d6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8db  endfinally
0x8dc  leave.s  loc_8EA
0x8de  ldloc.s  4
0x8e0  brfalse.s loc_8E9
0x8e2  ldloc.s  4
0x8e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8e9  endfinally
0x8ea  ldloc.0
0x8eb  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x8f0  ldarg.0
0x8f1  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x8f6  ldstr    aCleanstaleacti// "CleanStaleActionCards"
0x8fb  ldarg.0
0x8fc  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x901  ldstr    aAsynchandlerAc_3// "AsyncHandler::ActionCardAsyncOperation:"...
0x906  ldloc.0
0x907  callvirt instance int64 [System]System.Diagnostics.Stopwatch::get_ElapsedMilliseconds()
0x90c  ldstr    aTotally0Record// "Totally {0} records deleted from Action"...
0x911  ldloc.1
0x912  box      [mscorlib]System.Int32
0x917  ldloc.0
0x918  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x91d  box      [mscorlib]System.TimeSpan
0x922  call     string [mscorlib]System.String::Format(string, object, object)
0x927  ldsfld   string [mscorlib]System.String::Empty
0x92c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x931  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardTimeTaken(string, valuetype [mscorlib]System.Guid, string, int64, string, string, valuetype [mscorlib]System.Guid)
0x936  leave.s  loc_975
0x938  stloc.s  6
0x93a  ldloc.0
0x93b  callvirt instance void [System]System.Diagnostics.Stopwatch::Stop()
0x940  ldarg.0
0x941  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_cardsTrace
0x946  ldarg.0
0x947  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_organizationId
0x94c  ldstr    aAsynchandlerAc_3// "AsyncHandler::ActionCardAsyncOperation:"...
0x951  ldc.i4.3
0x952  ldstr    aErrorOccuredWh// "Error Occured while removing the old Ac"...
0x957  ldloc.s  6
0x959  callvirt instance string [mscorlib]System.Object::ToString()
0x95e  call     string [mscorlib]System.String::Format(string, object)
0x963  ldsfld   string [mscorlib]System.String::Empty
0x968  ldarg.0
0x969  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ActionCardAsyncOperation::_ownerId
0x96e  callvirt instance void [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ActionCardEventSource::ActionCardError(valuetype [mscorlib]System.Guid, string, int32, string, string, valuetype [mscorlib]System.Guid)
0x973  leave.s  loc_975
0x975  ret
```
