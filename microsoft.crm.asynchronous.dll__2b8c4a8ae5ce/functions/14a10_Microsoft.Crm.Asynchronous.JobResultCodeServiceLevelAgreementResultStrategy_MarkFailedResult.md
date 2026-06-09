# Microsoft.Crm.Asynchronous.JobResultCodeServiceLevelAgreementResultStrategy::MarkFailedResult

- ea: `0x14a10`
- end: `0x14a83`
- name: `Microsoft.Crm.Asynchronous.JobResultCodeServiceLevelAgreementResultStrategy::MarkFailedResult`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x14970`

## callees

- `0x12f00`
- `0x12f10`
- `0x12f20`
- `0x14a10`
- `0x14a90`

## pseudocode

```c

```

## disassembly

```asm
0x14a10  ldarg.1
0x14a11  isinst   Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError
0x14a16  stloc.0
0x14a17  ldloc.0
0x14a18  ldnull
0x14a19  cgt.un
0x14a1b  ldsfld   string [mscorlib]System.String::Empty
0x14a20  stloc.1
0x14a21  ldsfld   string [mscorlib]System.String::Empty
0x14a26  stloc.2
0x14a27  ldc.i4.3
0x14a28  stloc.3
0x14a29  brfalse.s loc_14A79
0x14a2b  ldloc.0
0x14a2c  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::get_ErrorCode()
0x14a31  call     int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmDatacenterService::ClassifyErrorCode(int32)
0x14a36  stloc.s  4
0x14a38  ldarg.0
0x14a39  ldloc.s  4
0x14a3b  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.TelemetryOperationResult Microsoft.Crm.Asynchronous.JobResultCodeServiceLevelAgreementResultStrategy::ConvertOperationResult(int32 operationResult)
0x14a40  stloc.3
0x14a41  ldloc.0
0x14a42  callvirt instance string Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::get_FriendlyMessage()
0x14a47  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x14a4c  brtrue.s loc_14A6B
0x14a4e  ldloc.0
0x14a4f  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::get_ErrorCode()
0x14a54  box      [mscorlib]System.Int32
0x14a59  ldstr    asc_2E170// ":"
0x14a5e  ldloc.0
0x14a5f  callvirt instance string Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::get_FriendlyMessage()
0x14a64  call     string [mscorlib]System.String::Concat(object, object, object)
0x14a69  br.s     loc_14A71
0x14a6b  ldloc.0
0x14a6c  callvirt instance string Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::get_ErrorMessage()
0x14a71  stloc.1
0x14a72  ldloc.0
0x14a73  callvirt instance string Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError::get_ErrorMessage()
0x14a78  stloc.2
0x14a79  ldarg.2
0x14a7a  ldloc.3
0x14a7b  ldloc.1
0x14a7c  ldloc.2
0x14a7d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryOperation::SetResult(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.TelemetryOperationResult, string, string)
0x14a82  ret
```
