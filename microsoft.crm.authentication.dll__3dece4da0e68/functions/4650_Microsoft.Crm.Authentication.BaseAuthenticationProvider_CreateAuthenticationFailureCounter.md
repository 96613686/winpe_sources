# Microsoft.Crm.Authentication.BaseAuthenticationProvider::CreateAuthenticationFailureCounter

- ea: `0x4650`
- end: `0x46ea`
- name: `Microsoft.Crm.Authentication.BaseAuthenticationProvider::CreateAuthenticationFailureCounter`
- size: `154`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2cf0`
- `0x66b0`
- `0xca90`

## callees

- `0x4650`

## pseudocode

```c

```

## disassembly

```asm
0x4650  ldarg.0
0x4651  ldarg.2
0x4652  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterFactory::GetCounter(string)
0x4657  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.Authentication.BaseAuthenticationProvider::_authenticationAttemptsInTheLastMinuteCounter
0x465c  ldarg.0
0x465d  ldarg.1
0x465e  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounterFactory::GetCounter(string)
0x4663  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.Authentication.BaseAuthenticationProvider::_authenticationFailuresInTheLastMinuteCounter
0x4668  ldarg.0
0x4669  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.Authentication.BaseAuthenticationProvider::_authenticationFailuresInTheLastMinuteCounter
0x466e  brfalse.s loc_469C
0x4670  ldarg.0
0x4671  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.Authentication.BaseAuthenticationProvider::_authenticationAttemptsInTheLastMinuteCounter
0x4676  brfalse.s loc_469C
0x4678  ldarg.0
0x4679  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.Authentication.BaseAuthenticationProvider::_authenticationAttemptsInTheLastMinuteCounter
0x467e  callvirt instance class [System]System.Diagnostics.PerformanceCounter [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter::get_PC()
0x4683  ldc.i4.0
0x4684  conv.i8
0x4685  callvirt instance void [System]System.Diagnostics.PerformanceCounter::set_RawValue(int64)
0x468a  ldarg.0
0x468b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter Microsoft.Crm.Authentication.BaseAuthenticationProvider::_authenticationFailuresInTheLastMinuteCounter
0x4690  callvirt instance class [System]System.Diagnostics.PerformanceCounter [Microsoft.Crm.Core]Microsoft.Crm.CrmPerformanceCounter::get_PC()
0x4695  ldc.i4.0
0x4696  conv.i8
0x4697  callvirt instance void [System]System.Diagnostics.PerformanceCounter::set_RawValue(int64)
0x469c  ldarg.0
0x469d  newobj   instance void [System]System.Timers.Timer::.ctor()
0x46a2  stfld    class [System]System.Timers.Timer Microsoft.Crm.Authentication.BaseAuthenticationProvider::_performanceMonitorTimer
0x46a7  ldarg.0
0x46a8  ldfld    class [System]System.Timers.Timer Microsoft.Crm.Authentication.BaseAuthenticationProvider::_performanceMonitorTimer
0x46ad  ldarg.0
0x46ae  ldftn    instance void Microsoft.Crm.Authentication.BaseAuthenticationProvider::UpdateCounters(object sender, class [System]System.Timers.ElapsedEventArgs e)
0x46b4  newobj   instance void [System]System.Timers.ElapsedEventHandler::.ctor(object, native int)
0x46b9  callvirt instance void [System]System.Timers.Timer::add_Elapsed(class [System]System.Timers.ElapsedEventHandler)
0x46be  ldarg.0
0x46bf  ldfld    class [System]System.Timers.Timer Microsoft.Crm.Authentication.BaseAuthenticationProvider::_performanceMonitorTimer
0x46c4  ldc.r8   60000.0
0x46cd  callvirt instance void [System]System.Timers.Timer::set_Interval(float64)
0x46d2  ldarg.0
0x46d3  ldfld    class [System]System.Timers.Timer Microsoft.Crm.Authentication.BaseAuthenticationProvider::_performanceMonitorTimer
0x46d8  ldc.i4.1
0x46d9  callvirt instance void [System]System.Timers.Timer::set_Enabled(bool)
0x46de  ldarg.0
0x46df  ldfld    class [System]System.Timers.Timer Microsoft.Crm.Authentication.BaseAuthenticationProvider::_performanceMonitorTimer
0x46e4  callvirt instance void [System]System.Timers.Timer::Start()
0x46e9  ret
```
