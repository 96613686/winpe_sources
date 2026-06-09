# Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::ExecuteInternal

- ea: `0x10280`
- end: `0x10785`
- name: `Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::ExecuteInternal`
- size: `1285`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `broker_com_uri`

## callers

- `0x10790`

## callees

- `0xbf60`
- `0xbf70`
- `0xbf80`
- `0xbfa0`
- `0xbfc0`
- `0xbfd0`
- `0xbfe0`
- `0xc000`
- `0xc010`
- `0xc050`
- `0xc070`
- `0xc910`
- `0xda20`
- `0xdaf0`
- `0xdb40`
- `0xdb80`
- `0xf770`
- `0xf790`
- `0xf7a0`
- `0xf820`
- `0xf890`
- `0xf8b0`
- `0xf8e0`
- `0xf8f0`
- `0xf910`
- `0xfdd0`
- `0x100a0`
- `0x101c0`
- `0x101e0`
- `0x10240`
- `0x10280`
- `0x172a0`

## string_xrefs

- `0x106e4`: `Exception encountered during bootstrap execution.\n {0}`
- `0x10727`: `Bootstrap completed for rollup field {0}. Timing Details:\n{1}`

## pseudocode

```c

```

## disassembly

```asm
0x10280  newobj   instance void <>c__DisplayClass11_0::.ctor()
0x10285  stloc.0
0x10286  ldloc.0
0x10287  ldarg.0
0x10288  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x1028d  callvirt instance class Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_DataAccess()
0x10292  ldarg.0
0x10293  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x10298  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_AsyncEvent()
0x1029d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x102a2  callvirt instance string Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess::GetTimingInformation(valuetype [mscorlib]System.Guid asyncOperationId)
0x102a7  stfld    string <>c__DisplayClass11_0::oldTimingCsv
0x102ac  ldloc.0
0x102ad  ldloc.0
0x102ae  ldfld    string <>c__DisplayClass11_0::oldTimingCsv
0x102b3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x102b8  brtrue.s loc_102C2
0x102ba  ldloc.0
0x102bb  ldfld    string <>c__DisplayClass11_0::oldTimingCsv
0x102c0  br.s     loc_102C7
0x102c2  ldstr    aStepNameTimeIn// "Step Name,Time in Milliseconds\n"
0x102c7  stfld    string <>c__DisplayClass11_0::oldTimingCsv
0x102cc  ldloc.0
0x102cd  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<string, class Microsoft.Crm.Asynchronous.Rollups.TimeTracker>>::.ctor()
0x102d2  stfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<string, class Microsoft.Crm.Asynchronous.Rollups.TimeTracker>> <>c__DisplayClass11_0::timers
0x102d7  ldloc.0
0x102d8  ldftn    instance string <>c__DisplayClass11_0::<ExecuteInternal>b__0()
0x102de  newobj   instance void class [mscorlib]System.Func`1<string>::.ctor(object, native int)
0x102e3  stloc.1
0x102e4  ldarg.0
0x102e5  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x102ea  callvirt instance int32 Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_StepNumber()
0x102ef  stloc.2
0x102f0  ldarg.0
0x102f1  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x102f6  callvirt instance int32 Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_InitialValueCalculationStatus()
0x102fb  ldc.i4.3
0x102fc  bne.un.s loc_10343
0x102fe  ldnull
0x102ff  ldarg.0
0x10300  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x10305  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_AsyncEvent()
0x1030a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1030f  ldc.i4.s 0x15
0x10311  ldstr    aBootstrapInvok// "Bootstrap invoked when initial calculat"...
0x10316  ldc.i4.0
0x10317  newarr   [mscorlib]System.Object
0x1031c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x10321  ldarg.0
0x10322  call     instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Logger()
0x10327  ldstr    aBootstrapInvok// "Bootstrap invoked when initial calculat"...
0x1032c  ldc.i4.0
0x1032d  newarr   [mscorlib]System.Object
0x10332  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogWarning(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x10337  ldloc.1
0x10338  callvirt instance var<u1> class [mscorlib]System.Func`1<string>::Invoke()
0x1033d  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncSucceededResult::.ctor(string)
0x10342  ret
0x10343  ldarg.0
0x10344  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x10349  callvirt instance int32 Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_InitialValueCalculationStatus()
0x1034e  ldc.i4.4
0x1034f  bne.un   loc_103EF
0x10354  ldarg.0
0x10355  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x1035a  callvirt instance class Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_DataAccess()
0x1035f  callvirt instance int32 Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess::CleanupJobs()
0x10364  stloc.3
0x10365  ldarg.0
0x10366  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x1036b  ldloc.1
0x1036c  ldloca.s 4
0x1036e  callvirt instance bool Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::CheckForEarlyExitRequest(class [mscorlib]System.Func`1<string> getTimingCsv, [out] class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult& execute)
0x10373  brfalse.s loc_10388
0x10375  ldarg.0
0x10376  ldc.i4.1
0x10377  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::GetPostponeUntil(int32 retryCount)
0x1037c  ldloc.1
0x1037d  callvirt instance var<u1> class [mscorlib]System.Func`1<string>::Invoke()
0x10382  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor(valuetype [mscorlib]System.DateTime, string)
0x10387  ret
0x10388  ldloc.3
0x10389  ldc.i4.0
0x1038a  bgt.s    loc_10354
0x1038c  ldnull
0x1038d  ldarg.0
0x1038e  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x10393  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_AsyncEvent()
0x10398  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1039d  ldc.i4.s 0x15
0x1039f  ldstr    aBootstrapJobEx// "Bootstrap job execution has been failed"...
0x103a4  ldc.i4.0
0x103a5  newarr   [mscorlib]System.Object
0x103aa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x103af  ldarg.0
0x103b0  call     instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Logger()
0x103b5  ldstr    aBootstrapJobEx// "Bootstrap job execution has been failed"...
0x103ba  ldc.i4.0
0x103bb  newarr   [mscorlib]System.Object
0x103c0  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogError(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x103c5  ldstr    aInitialvalueca// "InitialValueCalculationStatus"
0x103ca  ldc.i4.4
0x103cb  stloc.s  5
0x103cd  ldloca.s 5
0x103cf  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BootstrapStatus
0x103d5  callvirt instance string [mscorlib]System.Object::ToString()
0x103da  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x103df  ldstr    aBootstrapJobEx// "Bootstrap job execution has been failed"...
0x103e4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x103e9  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0x103ee  ret
0x103ef  nop
0x103f0  br       loc_104EA
0x103f5  ldarg.0
0x103f6  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x103fb  ldloc.1
0x103fc  ldloca.s 6
0x103fe  callvirt instance bool Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::CheckForEarlyExitRequest(class [mscorlib]System.Func`1<string> getTimingCsv, [out] class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult& execute)
0x10403  brfalse.s loc_1040E
0x10405  ldloc.s  6
0x10407  stloc.s  0xA
0x10409  leave    loc_10782
0x1040e  ldarg.0
0x1040f  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x10414  callvirt instance class Microsoft.Crm.Asynchronous.Rollups.Bootstrap.StepFactory Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_StepFactory()
0x10419  ldloc.2
0x1041a  ldarg.0
0x1041b  call     instance class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Logger()
0x10420  callvirt instance class Microsoft.Crm.Asynchronous.Rollups.Bootstrap.IBootstrapStep Microsoft.Crm.Asynchronous.Rollups.Bootstrap.StepFactory::GetStep(int32 stepNumber, class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger logger)
0x10425  stloc.s  7
0x10427  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1042c  ldstr    a01_4// "{0} ({1})"
0x10431  ldc.i4.2
0x10432  newarr   [mscorlib]System.Object
0x10437  dup
0x10438  ldc.i4.0
0x10439  ldloc.s  7
0x1043b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10440  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x10445  stelem.ref
0x10446  dup
0x10447  ldc.i4.1
0x10448  ldloc.2
0x10449  box      [mscorlib]System.Int32
0x1044e  stelem.ref
0x1044f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10454  stloc.s  8
0x10456  newobj   instance void Microsoft.Crm.Asynchronous.Rollups.TimeTracker::.ctor()
0x1045b  stloc.s  9
0x1045d  ldloc.0
0x1045e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<string, class Microsoft.Crm.Asynchronous.Rollups.TimeTracker>> <>c__DisplayClass11_0::timers
0x10463  ldloc.s  8
0x10465  ldloc.s  9
0x10467  call     T0x2B000025
0x1046c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`2<string, class Microsoft.Crm.Asynchronous.Rollups.TimeTracker>>::Add(var<u1>)
0x10471  ldloc.s  9
0x10473  callvirt instance void Microsoft.Crm.Asynchronous.Rollups.TimeTracker::Start()
0x10478  ldloc.s  7
0x1047a  callvirt instance int32 Microsoft.Crm.Asynchronous.Rollups.Bootstrap.IBootstrapStep::Execute()
0x1047f  stloc.2
0x10480  leave.s  loc_1048A
0x10482  ldloc.s  9
0x10484  callvirt instance void Microsoft.Crm.Asynchronous.Rollups.TimeTracker::Finish()
0x10489  endfinally
0x1048a  call     class Microsoft.Crm.Asynchronous.Rollups.RollupAsyncEventSource Microsoft.Crm.Asynchronous.Rollups.RollupAsyncEventSource::get_Instance()
0x1048f  ldarg.0
0x10490  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x10495  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_AsyncEvent()
0x1049a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x1049f  ldarg.0
0x104a0  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x104a5  callvirt instance string Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_SourceEntityLogicalName()
0x104aa  ldarg.0
0x104ab  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x104b0  callvirt instance bool Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_UseHierarchies()
0x104b5  ldloc.2
0x104b6  ldarg.0
0x104b7  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x104bc  callvirt instance int32 Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_RetryCount()
0x104c1  ldloc.s  9
0x104c3  callvirt instance int64 Microsoft.Crm.Asynchronous.Rollups.TimeTracker::get_ElapsedTicks()
0x104c8  callvirt instance void Microsoft.Crm.Asynchronous.Rollups.RollupAsyncEventSource::BootstrapStepSuccess(valuetype [mscorlib]System.Guid orgId, string entityName, bool hierarchical, int32 stepNumber, int32 retryCount, int64 executionTime)
0x104cd  ldarg.0
0x104ce  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x104d3  callvirt instance class Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_DataAccess()
0x104d8  ldloc.2
0x104d9  ldc.i4.m1
0x104da  beq.s    loc_104DF
0x104dc  ldloc.2
0x104dd  br.s     loc_104E0
0x104df  ldc.i4.1
0x104e0  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x104e5  callvirt instance void Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess::SetBootstrapStepNumber(valuetype [mscorlib]System.Nullable`1<int32> value)
0x104ea  ldloc.2
0x104eb  ldc.i4.m1
0x104ec  bne.un   loc_103F5
0x104f1  leave    loc_10776
0x104f6  stloc.s  0xB
0x104f8  ldarg.0
0x104f9  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x104fe  callvirt instance int32 Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_RetryCount()
0x10503  call     int32 Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_BootstrapRollupFailureMaxRetryCount()
0x10508  bge.s    loc_10520
0x1050a  ldloc.s  0xB
0x1050c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x10511  ldstr    aTheCurrentJobI// "The current job is no longer in progres"...
0x10516  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1051b  brfalse  loc_1063D
0x10520  ldarg.0
0x10521  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x10526  callvirt instance int32 Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_RetryCount()
0x1052b  call     int32 Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_BootstrapRollupFailureMaxRetryCount()
0x10530  blt      loc_1062F
0x10535  ldarg.0
0x10536  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x1053b  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_AsyncEvent()
0x10540  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x10545  ldc.i4.s 0x15
0x10547  ldstr    aBootstrapJobFo// "Bootstrap job for rollup field with id="...
0x1054c  ldc.i4.2
0x1054d  newarr   [mscorlib]System.Object
0x10552  dup
0x10553  ldc.i4.0
0x10554  ldarg.0
0x10555  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x1055a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_RollupPropertiesId()
0x1055f  box      [mscorlib]System.Guid
0x10564  stelem.ref
0x10565  dup
0x10566  ldc.i4.1
0x10567  ldarg.0
0x10568  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x1056d  callvirt instance int32 Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_RetryCount()
0x10572  box      [mscorlib]System.Int32
0x10577  stelem.ref
0x10578  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1057d  ldstr    aInitialvalueca// "InitialValueCalculationStatus"
0x10582  ldc.i4.4
0x10583  stloc.s  5
0x10585  ldloca.s 5
0x10587  constrained. [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BootstrapStatus
0x1058d  callvirt instance string [mscorlib]System.Object::ToString()
0x10592  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x10597  ldarg.0
0x10598  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x1059d  callvirt instance class Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_DataAccess()
0x105a2  callvirt instance void Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess::ProcessFailureJob()
0x105a7  call     class Microsoft.Crm.Asynchronous.Rollups.RollupAsyncEventSource Microsoft.Crm.Asynchronous.Rollups.RollupAsyncEventSource::get_Instance()
0x105ac  ldarg.0
0x105ad  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x105b2  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_AsyncEvent()
0x105b7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x105bc  ldarg.0
0x105bd  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x105c2  callvirt instance string Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_SourceEntityLogicalName()
0x105c7  ldarg.0
0x105c8  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x105cd  callvirt instance bool Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_UseHierarchies()
0x105d2  ldloc.2
0x105d3  ldarg.0
0x105d4  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x105d9  callvirt instance int32 Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_RetryCount()
0x105de  ldloc.s  0xB
0x105e0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x105e5  callvirt instance string [mscorlib]System.Type::get_FullName()
0x105ea  callvirt instance void Microsoft.Crm.Asynchronous.Rollups.RollupAsyncEventSource::BootstrapStepFailure(valuetype [mscorlib]System.Guid orgId, string entityName, bool hierarchical, int32 stepNumber, int32 retryCount, string errorType)
0x105ef  ldarg.0
0x105f0  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x105f5  callvirt instance class Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_DataAccess()
0x105fa  callvirt instance int32 Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess::CleanupJobs()
0x105ff  stloc.s  0xC
0x10601  ldarg.0
0x10602  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x10607  ldloc.1
0x10608  ldloca.s 0xD
0x1060a  callvirt instance bool Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::CheckForEarlyExitRequest(class [mscorlib]System.Func`1<string> getTimingCsv, [out] class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult& execute)
0x1060f  brfalse.s loc_1062A
0x10611  ldarg.0
0x10612  ldc.i4.1
0x10613  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::GetPostponeUntil(int32 retryCount)
0x10618  ldloc.1
0x10619  callvirt instance var<u1> class [mscorlib]System.Func`1<string>::Invoke()
0x1061e  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncPausedResult::.ctor(valuetype [mscorlib]System.DateTime, string)
0x10623  stloc.s  0xA
0x10625  leave    loc_10782
0x1062a  ldloc.s  0xC
0x1062c  ldc.i4.0
0x1062d  bgt.s    loc_105EF
0x1062f  ldloc.s  0xB
0x10631  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(class [mscorlib]System.Exception)
0x10636  stloc.s  0xA
0x10638  leave    loc_10782
0x1063d  ldarg.0
0x1063e  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x10643  ldarg.0
0x10644  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapExecutor::get_Operation()
0x10649  callvirt instance int32 Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_RetryCount()
0x1064e  ldc.i4.1
0x1064f  add
0x10650  callvirt instance void Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::set_RetryCount(int32 value)
  ... truncated ...
```
