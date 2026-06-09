# Microsoft.Crm.Asynchronous.Rollups.RollupJob::<RetryWithBackOff>b__53_0

- ea: `0xdfe0`
- end: `0xe07d`
- name: `Microsoft.Crm.Asynchronous.Rollups.RollupJob::<RetryWithBackOff>b__53_0`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0xdc70`
- `0xdcb0`
- `0xdcf0`
- `0xdd10`
- `0xdd40`
- `0xdd50`
- `0xdd60`
- `0xddb0`
- `0xdf60`
- `0xdfe0`
- `0xe1f0`

## string_xrefs

- `0xe067`: `Unexpected sqlCommandResult encountered while trying to retry RollupJob : `

## pseudocode

```c

```

## disassembly

```asm
0xdfe0  ldarg.0
0xdfe1  ldfld    class Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier Microsoft.Crm.Asynchronous.Rollups.RollupJob::_jobModifier
0xdfe6  ldarg.0
0xdfe7  ldloca.s 0
0xdfe9  callvirt instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.RollupJobModifier::PostponeWithExponentialBackOff(class Microsoft.Crm.Asynchronous.Rollups.RollupJob rollupJob, [out] valuetype [mscorlib]System.DateTime& postponeUntilUtc)
0xdfee  stloc.1
0xdfef  ldloc.1
0xdff0  switch   loc_E01E, loc_E020, loc_E013, loc_E01C, loc_E01C, loc_E067, loc_E067
0xe011  br.s     loc_E067
0xe013  ldarg.0
0xe014  call     instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.RollupJob::Delete()
0xe019  pop
0xe01a  ldloc.1
0xe01b  ret
0xe01c  ldloc.1
0xe01d  ret
0xe01e  ldloc.1
0xe01f  ret
0xe020  ldarg.0
0xe021  ldloc.0
0xe022  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::set_PostponeUntil(valuetype [mscorlib]System.DateTime value)
0xe027  ldarg.0
0xe028  call     instance bool Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_ShouldRegardingObjectIdChange()
0xe02d  brfalse.s loc_E065
0xe02f  ldarg.0
0xe030  ldarg.0
0xe031  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_NewRegardingObjectId()
0xe036  stloc.2
0xe037  ldloca.s 2
0xe039  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0xe03e  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::set_RegardingObjectId(valuetype [mscorlib]System.Guid value)
0xe043  ldarg.0
0xe044  ldc.i4.1
0xe045  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::set_RetryCount(int32 value)
0xe04a  ldarg.0
0xe04b  ldloca.s 2
0xe04d  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xe053  ldloc.2
0xe054  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::set_NewRegardingObjectId(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> value)
0xe059  ldarg.0
0xe05a  ldarg.0
0xe05b  call     instance int32 Microsoft.Crm.Asynchronous.Rollups.RollupJob::get_CurrentDepthProcessed()
0xe060  call     instance void Microsoft.Crm.Asynchronous.Rollups.RollupJob::set_DepthProcessed(int32 value)
0xe065  ldloc.1
0xe066  ret
0xe067  ldstr    aUnexpectedSqlc_0// "Unexpected sqlCommandResult encountered"...
0xe06c  ldloc.1
0xe06d  box      Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult
0xe072  call     string [mscorlib]System.String::Concat(object, object)
0xe077  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Rollup.CrmRollupException::.ctor(string)
0xe07c  throw
```
