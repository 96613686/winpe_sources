# Microsoft.Crm.Asynchronous.Rollups.JobExecutor::DeleteIfMaxRetryCountBreached

- ea: `0xcdd0`
- end: `0xce2b`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobExecutor::DeleteIfMaxRetryCountBreached`
- size: `91`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xcca0`
- `0x16e20`

## callees

- `0xc8f0`
- `0xcdd0`
- `0xdd20`
- `0xdf20`
- `0xdf40`
- `0xdf60`

## pseudocode

```c

```

## disassembly

```asm
0xcdd0  ldarg.1
0xcdd1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IRollupPropertiesData Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_RollupProperties()
0xcdd6  brtrue.s loc_CDE1
0xcdd8  ldarg.1
0xcdd9  callvirt instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.RollupJob::Delete()
0xcdde  pop
0xcddf  ldc.i4.1
0xcde0  ret
0xcde1  ldarg.2
0xcde2  call     int32 Microsoft.Crm.Asynchronous.Rollups.RollupConfiguration::get_IncrementalRollupFailureMaxRetryCount()
0xcde7  ble.s    loc_CE29
0xcde9  ldarg.1
0xcdea  callvirt instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.RollupJob::UpdateRollupStateOnRegardingObject()
0xcdef  stloc.0
0xcdf0  ldloc.0
0xcdf1  ldc.i4.1
0xcdf2  beq.s    loc_CDF7
0xcdf4  ldloc.0
0xcdf5  brtrue.s loc_CE00
0xcdf7  ldarg.1
0xcdf8  callvirt instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.RollupJob::Delete()
0xcdfd  pop
0xcdfe  br.s     loc_CE27
0xce00  ldstr    aRetrycount_0// "retryCount"
0xce05  ldarga.s 2
0xce07  call     instance string [mscorlib]System.Int32::ToString()
0xce0c  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xce11  ldstr    aIsrollupjobfai// "IsRollupJobFailedAfterRetries"
0xce16  ldstr    aTrue// "True"
0xce1b  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0xce20  ldarg.1
0xce21  callvirt instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.RollupJob::MarkAsFailed()
0xce26  pop
0xce27  ldc.i4.1
0xce28  ret
0xce29  ldc.i4.0
0xce2a  ret
```
