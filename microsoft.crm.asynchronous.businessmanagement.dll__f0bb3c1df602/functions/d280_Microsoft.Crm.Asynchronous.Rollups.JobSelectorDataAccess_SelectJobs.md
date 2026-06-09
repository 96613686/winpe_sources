# Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::SelectJobs

- ea: `0xd280`
- end: `0xd2de`
- name: `Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::SelectJobs`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0xd190`

## callees

- `0xd210`
- `0xd280`
- `0xd5a0`
- `0xd880`
- `0xe630`
- `0x16f50`

## pseudocode

```c

```

## disassembly

```asm
0xd280  newobj   instance void <>c__DisplayClass11_0::.ctor()
0xd285  stloc.0
0xd286  ldloc.0
0xd287  ldarg.0
0xd288  stfld    class Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess <>c__DisplayClass11_0::<>4__this
0xd28d  ldloc.0
0xd28e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Rollups.RollupJob>::.ctor()
0xd293  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Rollups.RollupJob> <>c__DisplayClass11_0::jobs
0xd298  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0xd29d  stloc.1
0xd29e  ldarg.0
0xd29f  ldloc.1
0xd2a0  ldc.i4.1
0xd2a1  call     instance void Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::SetupDbCommandForUpdate(class [System.Data]System.Data.IDbCommand crmDbCommand, bool outputData)
0xd2a6  ldarg.0
0xd2a7  call     instance class Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::get_DataAccess()
0xd2ac  ldloc.1
0xd2ad  ldloc.0
0xd2ae  ldftn    instance void <>c__DisplayClass11_0::<SelectJobs>b__0(object[] values)
0xd2b4  newobj   instance void class [mscorlib]System.Action`1<object[]>::.ctor(object, native int)
0xd2b9  callvirt instance int32 Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand command, class [mscorlib]System.Action`1<object[]> recordProcessor)
0xd2be  pop
0xd2bf  leave.s  loc_D2CB
0xd2c1  ldloc.1
0xd2c2  brfalse.s loc_D2CA
0xd2c4  ldloc.1
0xd2c5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd2ca  endfinally
0xd2cb  ldarg.0
0xd2cc  ldloc.0
0xd2cd  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Rollups.RollupJob> <>c__DisplayClass11_0::jobs
0xd2d2  call     instance void Microsoft.Crm.Asynchronous.Rollups.JobSelectorDataAccess::RemoveDuplicates(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Rollups.RollupJob> allJobs)
0xd2d7  ldloc.0
0xd2d8  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.Rollups.RollupJob> <>c__DisplayClass11_0::jobs
0xd2dd  ret
```
