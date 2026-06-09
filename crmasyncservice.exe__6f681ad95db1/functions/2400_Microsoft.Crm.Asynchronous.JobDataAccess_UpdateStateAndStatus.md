# Microsoft.Crm.Asynchronous.JobDataAccess::UpdateStateAndStatus

- ea: `0x2400`
- end: `0x278f`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::UpdateStateAndStatus`
- size: `911`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2360`
- `0x2400`
- `0xa7d0`

## string_xrefs

- `0x26c9`: `{0}: Updated {1} jobs.`

## pseudocode

```c

```

## disassembly

```asm
0x2400  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x2405  stloc.0
0x2406  ldsfld   string [mscorlib]System.String::Empty
0x240b  stloc.1
0x240c  ldsfld   string [mscorlib]System.String::Empty
0x2411  stloc.2
0x2412  ldarg.1
0x2413  brfalse.s loc_2440
0x2415  ldarg.1
0x2416  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRescheduleEventResult::get_RecurrenceStartTime()
0x241b  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x2420  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x2425  brfalse.s loc_2440
0x2427  ldstr    aRecurrencestar// ", RecurrenceStartTime = @recurrenceStar"...
0x242c  stloc.1
0x242d  ldarg.1
0x242e  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRescheduleEventResult::get_RecurrencePattern()
0x2433  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2438  brtrue.s loc_2440
0x243a  ldstr    aRecurrencepatt// ", RecurrencePattern = @recurrencePatter"...
0x243f  stloc.2
0x2440  ldloc.0
0x2441  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2446  ldarg.0
0x2447  call     instance bool Microsoft.Crm.Asynchronous.JobDataAccess::UpdateLastResultData()
0x244c  brtrue.s loc_2455
0x244e  ldsfld   string Microsoft.Crm.Asynchronous.JobDataAccess::_updateStateAndStatusCommand
0x2453  br.s     loc_245A
0x2455  ldsfld   string Microsoft.Crm.Asynchronous.JobDataAccess::_updateStateAndStatusWithLastResultDataCommand
0x245a  ldc.i4.2
0x245b  newarr   [mscorlib]System.Object
0x2460  dup
0x2461  ldc.i4.0
0x2462  ldloc.1
0x2463  stelem.ref
0x2464  dup
0x2465  ldc.i4.1
0x2466  ldloc.2
0x2467  stelem.ref
0x2468  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x246d  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2472  ldloc.0
0x2473  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x2478  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x247d  stloc.3
0x247e  ldloc.3
0x247f  ldstr    aNewstate// "@newState"
0x2484  ldarg.2
0x2485  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::get_NewState()
0x248a  box      [mscorlib]System.Int32
0x248f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2494  pop
0x2495  ldloc.3
0x2496  ldstr    aErrorcode// "@errorCode"
0x249b  ldarg.2
0x249c  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::get_ErrorCode()
0x24a1  box      [mscorlib]System.Int32
0x24a6  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x24ab  pop
0x24ac  ldloc.3
0x24ad  ldstr    aNextruntime// "@nextRunTime"
0x24b2  ldarg.2
0x24b3  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::get_NextOccurrence()
0x24b8  box      [mscorlib]System.DateTime
0x24bd  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x24c2  pop
0x24c3  ldloc.3
0x24c4  ldstr    aJobid// "@jobId"
0x24c9  ldarg.2
0x24ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::get_EventId()
0x24cf  box      [mscorlib]System.Guid
0x24d4  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x24d9  pop
0x24da  ldloc.3
0x24db  ldstr    aModifiedon// "@modifiedOn"
0x24e0  ldarg.0
0x24e1  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x24e6  box      [mscorlib]System.DateTime
0x24eb  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x24f0  pop
0x24f1  ldarg.0
0x24f2  call     instance bool Microsoft.Crm.Asynchronous.JobDataAccess::UpdateLastResultData()
0x24f7  brfalse.s loc_2536
0x24f9  ldloc.3
0x24fa  ldstr    aResultdata// "@resultData"
0x24ff  ldarg.2
0x2500  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::get_ErrorMessage()
0x2505  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x250a  brtrue.s loc_2514
0x250c  ldarg.2
0x250d  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::get_ErrorMessage()
0x2512  br.s     loc_2519
0x2514  ldsfld   string [mscorlib]System.String::Empty
0x2519  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x251e  pop
0x251f  ldloc.3
0x2520  ldstr    aExecutiontime// "@executionTime"
0x2525  ldarg.2
0x2526  callvirt instance float64 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::get_ExecutionTime()
0x252b  box      [mscorlib]System.Double
0x2530  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2535  pop
0x2536  ldarg.1
0x2537  brfalse.s loc_25AC
0x2539  ldloc.3
0x253a  ldstr    aRecurrencestar_0// "@recurrenceStartTime"
0x253f  ldarg.1
0x2540  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRescheduleEventResult::get_RecurrenceStartTime()
0x2545  box      [mscorlib]System.DateTime
0x254a  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x254f  pop
0x2550  ldarg.1
0x2551  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRescheduleEventResult::get_RecurrencePattern()
0x2556  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x255b  brtrue.s loc_256F
0x255d  ldloc.3
0x255e  ldstr    aRecurrencepatt_0// "@recurrencePattern"
0x2563  ldarg.1
0x2564  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRescheduleEventResult::get_RecurrencePattern()
0x2569  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x256e  pop
0x256f  ldarg.0
0x2570  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessSharedBase::get_OrganizationId()
0x2575  ldc.i4.s 0x15
0x2577  ldstr    aUpdatingRecurr// "Updating Recurrence for maintenance job"...
0x257c  ldc.i4.3
0x257d  newarr   [mscorlib]System.Object
0x2582  dup
0x2583  ldc.i4.0
0x2584  ldarg.2
0x2585  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::get_EventId()
0x258a  box      [mscorlib]System.Guid
0x258f  stelem.ref
0x2590  dup
0x2591  ldc.i4.1
0x2592  ldarg.1
0x2593  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRescheduleEventResult::get_RecurrencePattern()
0x2598  stelem.ref
0x2599  dup
0x259a  ldc.i4.2
0x259b  ldarg.1
0x259c  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRescheduleEventResult::get_RecurrenceStartTime()
0x25a1  box      [mscorlib]System.DateTime
0x25a6  stelem.ref
0x25a7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25ac  nop
0x25ad  newobj   instance void <>c__DisplayClass11_0::.ctor()
0x25b2  stloc.s  4
0x25b4  ldloc.s  4
0x25b6  ldarg.0
0x25b7  stfld    class Microsoft.Crm.Asynchronous.JobDataAccess <>c__DisplayClass11_0::<>4__this
0x25bc  ldloc.s  4
0x25be  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x25c3  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass11_0::organizationId
0x25c8  ldloc.s  4
0x25ca  ldc.i4.0
0x25cb  stfld    int32 <>c__DisplayClass11_0::operationType
0x25d0  ldloc.s  4
0x25d2  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x25d7  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass11_0::operationStartTime
0x25dc  ldloc.s  4
0x25de  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x25e3  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass11_0::operationEndTime
0x25e8  ldarg.0
0x25e9  ldloc.0
0x25ea  ldloc.s  4
0x25ec  ldftn    instance void <>c__DisplayClass11_0::<UpdateStateAndStatus>b__0(object[] values)
0x25f2  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x25f7  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x25fc  stloc.s  5
0x25fe  ldarg.2
0x25ff  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::get_ErrorCode()
0x2604  ldc.i4.0
0x2605  ceq
0x2607  stloc.s  6
0x2609  ldloc.s  6
0x260b  brfalse.s loc_261B
0x260d  ldloc.s  4
0x260f  ldfld    int32 <>c__DisplayClass11_0::operationType
0x2614  ldc.i4.s 0x1A
0x2616  beq      loc_26C0
0x261b  ldarg.0
0x261c  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x2621  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_EventLog()
0x2626  ldloc.s  6
0x2628  brtrue.s loc_262D
0x262a  ldc.i4.2
0x262b  br.s     loc_262E
0x262d  ldc.i4.4
0x262e  ldloc.s  6
0x2630  brtrue.s loc_263A
0x2632  ldc.i4   0x8000440D
0x2637  conv.u8
0x2638  br.s     loc_2640
0x263a  ldc.i4   0x4000440C
0x263f  conv.i8
0x2640  ldc.i4.7
0x2641  newarr   [mscorlib]System.Object
0x2646  dup
0x2647  ldc.i4.0
0x2648  ldarg.0
0x2649  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x264e  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x2653  stelem.ref
0x2654  dup
0x2655  ldc.i4.1
0x2656  ldloc.s  4
0x2658  ldfld    int32 <>c__DisplayClass11_0::operationType
0x265d  box      [mscorlib]System.Int32
0x2662  stelem.ref
0x2663  dup
0x2664  ldc.i4.2
0x2665  ldloc.s  4
0x2667  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass11_0::organizationId
0x266c  box      [mscorlib]System.Guid
0x2671  stelem.ref
0x2672  dup
0x2673  ldc.i4.3
0x2674  ldloc.s  4
0x2676  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass11_0::operationStartTime
0x267b  box      [mscorlib]System.DateTime
0x2680  stelem.ref
0x2681  dup
0x2682  ldc.i4.4
0x2683  ldloc.s  4
0x2685  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass11_0::operationEndTime
0x268a  box      [mscorlib]System.DateTime
0x268f  stelem.ref
0x2690  dup
0x2691  ldc.i4.5
0x2692  ldarg.2
0x2693  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::get_ErrorCode()
0x2698  box      [mscorlib]System.Int32
0x269d  stelem.ref
0x269e  dup
0x269f  ldc.i4.6
0x26a0  ldarg.2
0x26a1  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::get_ErrorMessage()
0x26a6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x26ab  brtrue.s loc_26B5
0x26ad  ldarg.2
0x26ae  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::get_ErrorMessage()
0x26b3  br.s     loc_26BA
0x26b5  ldsfld   string [mscorlib]System.String::Empty
0x26ba  stelem.ref
0x26bb  call     void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventLogHelper::LogEvent(class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x26c0  ldloc.s  4
0x26c2  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass11_0::organizationId
0x26c7  ldc.i4.s 0x15
0x26c9  ldstr    a0Updated1Jobs// "{0}: Updated {1} jobs."
0x26ce  ldc.i4.2
0x26cf  newarr   [mscorlib]System.Object
0x26d4  dup
0x26d5  ldc.i4.0
0x26d6  ldarg.0
0x26d7  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x26dc  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x26e1  stelem.ref
0x26e2  dup
0x26e3  ldc.i4.1
0x26e4  ldloc.s  5
0x26e6  box      [mscorlib]System.Int32
0x26eb  stelem.ref
0x26ec  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x26f1  leave    loc_278E
0x26f6  stloc.s  7
0x26f8  ldloc.s  7
0x26fa  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x26ff  brtrue.s loc_2713
0x2701  ldloc.s  7
0x2703  isinst   [System.Data]System.Data.SqlClient.SqlException
0x2708  brtrue.s loc_2713
0x270a  ldloc.s  7
0x270c  isinst   [mscorlib]System.InvalidOperationException
0x2711  brfalse.s loc_2780
0x2713  ldarg.2
0x2714  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventState::get_ErrorCode()
0x2719  ldc.i4.2
0x271a  bne.un.s loc_274E
0x271c  ldarg.0
0x271d  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x2722  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_EventLog()
0x2727  ldc.i4.1
0x2728  ldc.i4   0xC000441A
0x272d  conv.u8
0x272e  ldc.i4.2
0x272f  newarr   [mscorlib]System.Object
0x2734  dup
0x2735  ldc.i4.0
0x2736  ldarg.0
0x2737  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x273c  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x2741  stelem.ref
0x2742  dup
0x2743  ldc.i4.1
0x2744  ldloc.s  7
0x2746  stelem.ref
0x2747  call     void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventLogHelper::LogEvent(class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x274c  br.s     loc_2782
0x274e  ldarg.0
  ... truncated ...
```
