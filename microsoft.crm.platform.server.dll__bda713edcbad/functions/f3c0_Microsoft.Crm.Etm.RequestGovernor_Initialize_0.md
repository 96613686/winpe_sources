# Microsoft.Crm.Etm.RequestGovernor::Initialize_0

- ea: `0xf3c0`
- end: `0xf56c`
- name: `Microsoft.Crm.Etm.RequestGovernor::Initialize_0`
- size: `428`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf3a0`
- `0xf6f0`

## callees

- `0xdcb0`
- `0xdcc0`
- `0xdcd0`
- `0xdce0`
- `0xf3c0`
- `0xf570`
- `0xf6b0`
- `0xf880`
- `0xfd70`

## string_xrefs

- `0xf3c1`: `configuration`
- `0xf51f`: `RequestGovernor received exception during initialization {0}`

## pseudocode

```c

```

## disassembly

```asm
0xf3c0  ldarg.1
0xf3c1  ldstr    aConfiguration// "configuration"
0xf3c6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xf3cb  ldarg.0
0xf3cc  ldarg.1
0xf3cd  stfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf3d2  ldc.i4.0
0xf3d3  stsfld   bool Microsoft.Crm.Etm.RequestGovernor::_governorEnabled
0xf3d8  ldarg.0
0xf3d9  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer Microsoft.Crm.Etm.RequestGovernor::_backgroundCollectionTimer
0xf3de  brfalse.s loc_F3FD
0xf3e0  ldarg.0
0xf3e1  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer Microsoft.Crm.Etm.RequestGovernor::_backgroundCollectionTimer
0xf3e6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer::Stop()
0xf3eb  ldarg.0
0xf3ec  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer Microsoft.Crm.Etm.RequestGovernor::_backgroundCollectionTimer
0xf3f1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer::Dispose()
0xf3f6  ldarg.0
0xf3f7  ldnull
0xf3f8  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer Microsoft.Crm.Etm.RequestGovernor::_backgroundCollectionTimer
0xf3fd  ldarg.0
0xf3fe  call     instance void Microsoft.Crm.Etm.RequestGovernor::StopBackgroundPerformanceMonitorThread()
0xf403  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0xf408  brfalse.s loc_F40B
0xf40a  ret
0xf40b  nop
0xf40c  ldarg.0
0xf40d  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf412  callvirt instance bool Microsoft.Crm.Etm.IConfiguration::get_Enabled()
0xf417  stsfld   bool Microsoft.Crm.Etm.RequestGovernor::_governorEnabled
0xf41c  ldsfld   bool Microsoft.Crm.Etm.RequestGovernor::_governorEnabled
0xf421  brfalse.s loc_F434
0xf423  ldarg.0
0xf424  newobj   instance void Microsoft.Crm.Etm.DataManager::.ctor()
0xf429  stfld    class Microsoft.Crm.Etm.DataManager Microsoft.Crm.Etm.RequestGovernor::_dataManager
0xf42e  ldarg.0
0xf42f  call     instance void Microsoft.Crm.Etm.RequestGovernor::InitializeProviders()
0xf434  ldc.i4.0
0xf435  stloc.0
0xf436  ldc.i4.0
0xf437  stloc.1
0xf438  ldarg.0
0xf439  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IDataCollector> Microsoft.Crm.Etm.RequestGovernor::_dataCollectors
0xf43e  brfalse.s loc_F44C
0xf440  ldarg.0
0xf441  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IDataCollector> Microsoft.Crm.Etm.RequestGovernor::_dataCollectors
0xf446  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IDataCollector>::get_Count()
0xf44b  stloc.0
0xf44c  ldarg.0
0xf44d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IThrottleProvider> Microsoft.Crm.Etm.RequestGovernor::_throttleProviders
0xf452  brfalse.s loc_F460
0xf454  ldarg.0
0xf455  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IThrottleProvider> Microsoft.Crm.Etm.RequestGovernor::_throttleProviders
0xf45a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IThrottleProvider>::get_Count()
0xf45f  stloc.1
0xf460  ldloc.0
0xf461  brtrue.s loc_F469
0xf463  ldc.i4.0
0xf464  stsfld   bool Microsoft.Crm.Etm.RequestGovernor::_governorEnabled
0xf469  ldc.i4.4
0xf46a  ldc.i4   0x40004332
0xf46f  conv.i8
0xf470  ldc.i4.5
0xf471  newarr   [mscorlib]System.Object
0xf476  dup
0xf477  ldc.i4.0
0xf478  ldloca.s 0
0xf47a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf47f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf484  stelem.ref
0xf485  dup
0xf486  ldc.i4.1
0xf487  ldloca.s 1
0xf489  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf48e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xf493  stelem.ref
0xf494  dup
0xf495  ldc.i4.2
0xf496  ldsfld   bool Microsoft.Crm.Etm.RequestGovernor::_governorEnabled
0xf49b  brtrue.s loc_F4A4
0xf49d  ldstr    aOff// "Off"
0xf4a2  br.s     loc_F4A9
0xf4a4  ldstr    aOn// "On"
0xf4a9  stelem.ref
0xf4aa  dup
0xf4ab  ldc.i4.3
0xf4ac  ldarg.0
0xf4ad  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf4b2  callvirt instance bool Microsoft.Crm.Etm.IConfiguration::get_StatisticsUpdateEnabled()
0xf4b7  brtrue.s loc_F4C0
0xf4b9  ldstr    aOff// "Off"
0xf4be  br.s     loc_F4C5
0xf4c0  ldstr    aOn// "On"
0xf4c5  stelem.ref
0xf4c6  dup
0xf4c7  ldc.i4.4
0xf4c8  ldarg.0
0xf4c9  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf4ce  callvirt instance bool Microsoft.Crm.Etm.IConfiguration::get_ThrottlingEnabled()
0xf4d3  brfalse.s loc_F4E2
0xf4d5  ldarg.0
0xf4d6  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf4db  callvirt instance bool Microsoft.Crm.Etm.IConfiguration::get_ServerThrottlingDisabled()
0xf4e0  brfalse.s loc_F4E9
0xf4e2  ldstr    aOff// "Off"
0xf4e7  br.s     loc_F4EE
0xf4e9  ldstr    aOn// "On"
0xf4ee  stelem.ref
0xf4ef  call     void Microsoft.Crm.Etm.RequestGovernor::LogEvent(valuetype [System]System.Diagnostics.EventLogEntryType type, int64 eventId, object[] values)
0xf4f4  leave.s  loc_F56B
0xf4f6  stloc.2
0xf4f7  ldc.i4.0
0xf4f8  stsfld   bool Microsoft.Crm.Etm.RequestGovernor::_governorEnabled
0xf4fd  ldc.i4.1
0xf4fe  ldc.i4   0xC0004331
0xf503  conv.u8
0xf504  ldc.i4.1
0xf505  newarr   [mscorlib]System.Object
0xf50a  dup
0xf50b  ldc.i4.0
0xf50c  ldloc.2
0xf50d  callvirt instance string [mscorlib]System.Object::ToString()
0xf512  stelem.ref
0xf513  call     void Microsoft.Crm.Etm.RequestGovernor::LogEvent(valuetype [System]System.Diagnostics.EventLogEntryType type, int64 eventId, object[] values)
0xf518  ldloc.2
0xf519  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xf51e  ldc.i4.7
0xf51f  ldstr    aRequestgoverno_0// "RequestGovernor received exception duri"...
0xf524  ldc.i4.1
0xf525  newarr   [mscorlib]System.Object
0xf52a  dup
0xf52b  ldc.i4.0
0xf52c  ldloc.2
0xf52d  stelem.ref
0xf52e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf533  leave.s  loc_F56B
0xf535  ldsfld   bool Microsoft.Crm.Etm.RequestGovernor::_governorEnabled
0xf53a  brfalse.s loc_F554
0xf53c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xf541  ldc.i4.7
0xf542  ldstr    aRequestgoverno_1// "RequestGovernor enabled"
0xf547  ldc.i4.0
0xf548  newarr   [mscorlib]System.Object
0xf54d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf552  br.s     loc_F56A
0xf554  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xf559  ldc.i4.7
0xf55a  ldstr    aRequestgoverno_2// "RequestGovernor disabled"
0xf55f  ldc.i4.0
0xf560  newarr   [mscorlib]System.Object
0xf565  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf56a  endfinally
0xf56b  ret
```
