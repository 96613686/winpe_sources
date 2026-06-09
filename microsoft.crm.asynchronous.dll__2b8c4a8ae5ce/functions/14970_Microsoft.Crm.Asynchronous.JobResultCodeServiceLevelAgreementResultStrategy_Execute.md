# Microsoft.Crm.Asynchronous.JobResultCodeServiceLevelAgreementResultStrategy::Execute

- ea: `0x14970`
- end: `0x14a07`
- name: `Microsoft.Crm.Asynchronous.JobResultCodeServiceLevelAgreementResultStrategy::Execute`
- size: `151`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x14970`
- `0x14a10`
- `0x14ab0`

## pseudocode

```c

```

## disassembly

```asm
0x14970  ldarg.1
0x14971  ldstr    aOperationCanno// "operation cannot be null."
0x14976  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1497b  ldarg.0
0x1497c  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Asynchronous.JobResultCodeServiceLevelAgreementResultStrategy::result
0x14981  isinst   Microsoft.Crm.Asynchronous.AsyncHandlerResultWithError
0x14986  brfalse.s loc_14996
0x14988  ldarg.0
0x14989  ldarg.0
0x1498a  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Asynchronous.JobResultCodeServiceLevelAgreementResultStrategy::result
0x1498f  ldarg.1
0x14990  call     instance void Microsoft.Crm.Asynchronous.JobResultCodeServiceLevelAgreementResultStrategy::MarkFailedResult(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult asyncResult, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryOperation operation)
0x14995  ret
0x14996  ldarg.0
0x14997  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Asynchronous.JobResultCodeServiceLevelAgreementResultStrategy::result
0x1499c  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult::get_ResultCode()
0x149a1  stloc.0
0x149a2  ldloc.0
0x149a3  ldc.i4.s 0x16
0x149a5  bgt.s    loc_149C5
0x149a7  ldloc.0
0x149a8  brfalse.s loc_149F9
0x149aa  ldloc.0
0x149ab  ldc.i4.s 0xA
0x149ad  beq.s    loc_149F9
0x149af  ldloc.0
0x149b0  ldc.i4.s 0x14
0x149b2  sub
0x149b3  switch   loc_149F9, loc_149F9, loc_149F9
0x149c4  ret
0x149c5  ldloc.0
0x149c6  ldc.i4.s 0x1E
0x149c8  sub
0x149c9  switch   loc_149F9, loc_149EB, loc_149F9
0x149da  ldloc.0
0x149db  ldc.i4   0x3E8
0x149e0  beq.s    loc_149F9
0x149e2  ldloc.0
0x149e3  ldc.i4   0x3E9
0x149e8  beq.s    loc_149F9
0x149ea  ret
0x149eb  ldarg.0
0x149ec  ldarg.0
0x149ed  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Asynchronous.JobResultCodeServiceLevelAgreementResultStrategy::result
0x149f2  ldarg.1
0x149f3  call     instance void Microsoft.Crm.Asynchronous.JobResultCodeServiceLevelAgreementResultStrategy::MarkFailedResult(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult asyncResult, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryOperation operation)
0x149f8  ret
0x149f9  ldarg.0
0x149fa  ldarg.0
0x149fb  ldfld    class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult Microsoft.Crm.Asynchronous.JobResultCodeServiceLevelAgreementResultStrategy::result
0x14a00  ldarg.1
0x14a01  call     instance void Microsoft.Crm.Asynchronous.JobResultCodeServiceLevelAgreementResultStrategy::MarkSuccessResult(class [Microsoft.Crm]Microsoft.Crm.IGenericHandlerResult asyncResult, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.ITelemetryOperation operation)
0x14a06  ret
```
