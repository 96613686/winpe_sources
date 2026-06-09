# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::CreateDateTimeConversionTrackerEntryInternal

- ea: `0x2990`
- end: `0x2a52`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::CreateDateTimeConversionTrackerEntryInternal`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2900`

## callees

- `0x2990`

## string_xrefs

- `0x2990`: `INSERT INTO [dbo].[DateTimeConversionTracker]([EntityId],[AttributeId],[Status],[CreatedOn],[ModifiedOn]) VALUES\n('{0}','{1}',{2},'{3}','{4}')`
- `0x29f0`: `CreateDateTimeConversionTrackerEntryInternal`

## pseudocode

```c

```

## disassembly

```asm
0x2990  ldstr    aInsertIntoDboD// "INSERT INTO [dbo].[DateTimeConversionTr"...
0x2995  stloc.0
0x2996  ldarg.2
0x2997  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::CreateCommand()
0x299c  stloc.1
0x299d  ldloc.1
0x299e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29a3  ldloc.0
0x29a4  ldc.i4.5
0x29a5  newarr   [mscorlib]System.Object
0x29aa  dup
0x29ab  ldc.i4.0
0x29ac  ldarg.3
0x29ad  box      [mscorlib]System.Guid
0x29b2  stelem.ref
0x29b3  dup
0x29b4  ldc.i4.1
0x29b5  ldarg.s  5
0x29b7  box      [mscorlib]System.Guid
0x29bc  stelem.ref
0x29bd  dup
0x29be  ldc.i4.2
0x29bf  ldc.i4.2
0x29c0  box      [mscorlib]System.Int32
0x29c5  stelem.ref
0x29c6  dup
0x29c7  ldc.i4.3
0x29c8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x29cd  box      [mscorlib]System.DateTime
0x29d2  stelem.ref
0x29d3  dup
0x29d4  ldc.i4.4
0x29d5  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x29da  box      [mscorlib]System.DateTime
0x29df  stelem.ref
0x29e0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x29e5  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x29ea  ldloc.1
0x29eb  ldc.i4   0x1A1
0x29f0  ldstr    aCreatedatetime// "CreateDateTimeConversionTrackerEntryInt"...
0x29f5  ldstr    aDDbsShDccm2110_0// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x29fa  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x29ff  pop
0x2a00  leave.s  loc_2A51
0x2a02  stloc.2
0x2a03  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2a08  ldstr    aAsynchandlerCo_2// "AsyncHandler::ConvertDateAndTimeBehavio"...
0x2a0d  ldc.i4.3
0x2a0e  newarr   [mscorlib]System.Object
0x2a13  dup
0x2a14  ldc.i4.0
0x2a15  ldarg.1
0x2a16  stelem.ref
0x2a17  dup
0x2a18  ldc.i4.1
0x2a19  ldarg.s  4
0x2a1b  stelem.ref
0x2a1c  dup
0x2a1d  ldc.i4.2
0x2a1e  ldloc.2
0x2a1f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2a24  stelem.ref
0x2a25  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2a2a  stloc.3
0x2a2b  ldloc.2
0x2a2c  ldarg.0
0x2a2d  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::_asyncEvent
0x2a32  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x2a37  ldc.i4.s 0x15
0x2a39  ldloc.3
0x2a3a  ldc.i4.0
0x2a3b  newarr   [mscorlib]System.Object
0x2a40  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2a45  leave.s  loc_2A51
0x2a47  ldloc.1
0x2a48  brfalse.s loc_2A50
0x2a4a  ldloc.1
0x2a4b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2a50  endfinally
0x2a51  ret
```
