# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::RunStep

- ea: `0x61f0`
- end: `0x62b3`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::RunStep`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x5ed0`

## callees

- `0x61f0`
- `0x8950`
- `0x13ef0`
- `0x13f10`
- `0x13f60`
- `0x157a0`
- `0x157c0`
- `0x16370`
- `0x163a0`
- `0x163f0`
- `0x16540`
- `0x16550`

## string_xrefs

- `0x6246`: `Resource Booking Sync Service encountered an internal error in the {0} step.`
- `0x6267`: `ResourceBookingSyncService[{0}] error: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x61f0  ldarg.1
0x61f1  callvirt instance class SyncConfig SyncStep::get_Config()
0x61f6  stloc.0
0x61f7  call     bool RunTimeControl::get_IsExpired()
0x61fc  brtrue   loc_6297
0x6201  ldarg.0
0x6202  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6207  ldloc.0
0x6208  callvirt instance string SyncConfig::get_Name()
0x620d  ldloc.0
0x620e  callvirt instance string SyncConfig::get_Description()
0x6213  callvirt instance class Timer Metrics::AddTimer(string name, string description)
0x6218  pop
0x6219  ldarg.0
0x621a  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x621f  ldloc.0
0x6220  callvirt instance string SyncConfig::get_Name()
0x6225  ldc.i4.1
0x6226  callvirt instance void Metrics::StartTimer(string name, bool trace)
0x622b  ldarg.1
0x622c  callvirt instance class [mscorlib]System.Action`1<class SyncConfig> SyncStep::get_Action()
0x6231  ldarg.1
0x6232  callvirt instance class SyncConfig SyncStep::get_Config()
0x6237  callvirt instance void class [mscorlib]System.Action`1<class SyncConfig>::Invoke(var<u1>)
0x623c  leave.s  loc_62B2
0x623e  stloc.1
0x623f  ldarg.0
0x6240  ldc.i4   0xC0004663
0x6245  conv.u8
0x6246  ldstr    aResourceBookin_0// "Resource Booking Sync Service encounter"...
0x624b  ldloc.0
0x624c  callvirt instance string SyncConfig::get_Name()
0x6251  call     string [mscorlib]System.String::Format(string, object)
0x6256  ldloc.1
0x6257  callvirt instance string [mscorlib]System.Object::ToString()
0x625c  call     instance void Microsoft.Crm.Asynchronous.ResourceBookingSyncService::LogCrmTraceAndEventLog(int64 logId, string crmTraceMessage, string errorMessage)
0x6261  ldarg.0
0x6262  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x6267  ldstr    aResourcebookin_1// "ResourceBookingSyncService[{0}] error: "...
0x626c  ldloc.0
0x626d  callvirt instance string SyncConfig::get_Name()
0x6272  ldloc.1
0x6273  callvirt instance string [mscorlib]System.Exception::get_Message()
0x6278  call     string [mscorlib]System.String::Format(string, object, object)
0x627d  callvirt instance void Metrics::AddMessageAndTrace(string message)
0x6282  rethrow
0x6284  ldarg.0
0x6285  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x628a  ldloc.0
0x628b  callvirt instance string SyncConfig::get_Name()
0x6290  ldc.i4.1
0x6291  callvirt instance void Metrics::StopTimer(string name, bool trace)
0x6296  endfinally
0x6297  ldarg.0
0x6298  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x629d  ldstr    aSkippedStep0// "Skipped step: {0}"
0x62a2  ldloc.0
0x62a3  callvirt instance string SyncConfig::get_Name()
0x62a8  call     string [mscorlib]System.String::Format(string, object)
0x62ad  callvirt instance void Metrics::RunTimeExpired(string message)
0x62b2  ret
```
