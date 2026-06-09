# Microsoft.Crm.Asynchronous.JobDataAccess::TryCheckIfIsOutsideOfBusinessHour

- ea: `0x3b70`
- end: `0x3c49`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::TryCheckIfIsOutsideOfBusinessHour`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x3410`

## callees

- `0x3b70`
- `0x3f80`
- `0x3f90`
- `0x4340`

## string_xrefs

- `0x3b87`: `[DBUPDATES] Deployment settings for NonBusinessHourStartTimeOfDay ({0}) and/or NonBusinessHourEndTimeOfDay ({1}) have not been configured. Cannot determine if current time is outside of business hours.`

## pseudocode

```c

```

## disassembly

```asm
0x3b70  ldarg.0
0x3b71  ldc.i4.0
0x3b72  stind.i1
0x3b73  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_NonBusinessHourStartTimeOfDay()
0x3b78  stloc.0
0x3b79  call     int32 Microsoft.Crm.Asynchronous.JobDataAccessConstants::get_NonBusinessHourEndTimeOfDay()
0x3b7e  stloc.1
0x3b7f  ldloc.0
0x3b80  ldc.i4.0
0x3b81  blt.s    loc_3B87
0x3b83  ldloc.1
0x3b84  ldc.i4.0
0x3b85  bge.s    loc_3BAB
0x3b87  ldstr    aDbupdatesDeplo// "[DBUPDATES] Deployment settings for Non"...
0x3b8c  ldc.i4.2
0x3b8d  newarr   [mscorlib]System.Object
0x3b92  dup
0x3b93  ldc.i4.0
0x3b94  ldloc.0
0x3b95  box      [mscorlib]System.Int32
0x3b9a  stelem.ref
0x3b9b  dup
0x3b9c  ldc.i4.1
0x3b9d  ldloc.1
0x3b9e  box      [mscorlib]System.Int32
0x3ba3  stelem.ref
0x3ba4  call     void Microsoft.Crm.Asynchronous.JobManager::LogDBUpdateScheduledTelemetry(string messageFormat, object[] args)
0x3ba9  ldc.i4.0
0x3baa  ret
0x3bab  ldloc.0
0x3bac  ldloc.1
0x3bad  ble.s    loc_3BFC
0x3baf  ldarg.0
0x3bb0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x3bb5  stloc.2
0x3bb6  ldloca.s 2
0x3bb8  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToLocalTime()
0x3bbd  stloc.2
0x3bbe  ldloca.s 2
0x3bc0  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x3bc5  ldloc.0
0x3bc6  ldc.i4.0
0x3bc7  ldc.i4.0
0x3bc8  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x3bcd  call     bool [mscorlib]System.TimeSpan::op_GreaterThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x3bd2  brtrue.s loc_3BF8
0x3bd4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x3bd9  stloc.2
0x3bda  ldloca.s 2
0x3bdc  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToLocalTime()
0x3be1  stloc.2
0x3be2  ldloca.s 2
0x3be4  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x3be9  ldloc.1
0x3bea  ldc.i4.0
0x3beb  ldc.i4.0
0x3bec  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x3bf1  call     bool [mscorlib]System.TimeSpan::op_LessThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x3bf6  br.s     loc_3BF9
0x3bf8  ldc.i4.1
0x3bf9  stind.i1
0x3bfa  br.s     loc_3C47
0x3bfc  ldarg.0
0x3bfd  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x3c02  stloc.2
0x3c03  ldloca.s 2
0x3c05  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToLocalTime()
0x3c0a  stloc.2
0x3c0b  ldloca.s 2
0x3c0d  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x3c12  ldloc.0
0x3c13  ldc.i4.0
0x3c14  ldc.i4.0
0x3c15  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x3c1a  call     bool [mscorlib]System.TimeSpan::op_GreaterThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x3c1f  brfalse.s loc_3C45
0x3c21  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x3c26  stloc.2
0x3c27  ldloca.s 2
0x3c29  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToLocalTime()
0x3c2e  stloc.2
0x3c2f  ldloca.s 2
0x3c31  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::get_TimeOfDay()
0x3c36  ldloc.1
0x3c37  ldc.i4.0
0x3c38  ldc.i4.0
0x3c39  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x3c3e  call     bool [mscorlib]System.TimeSpan::op_LessThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x3c43  br.s     loc_3C46
0x3c45  ldc.i4.0
0x3c46  stind.i1
0x3c47  ldc.i4.1
0x3c48  ret
```
