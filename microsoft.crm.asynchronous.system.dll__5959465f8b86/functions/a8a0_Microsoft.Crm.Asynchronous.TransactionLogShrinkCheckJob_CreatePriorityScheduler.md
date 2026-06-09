# Microsoft.Crm.Asynchronous.TransactionLogShrinkCheckJob::CreatePriorityScheduler

- ea: `0xa8a0`
- end: `0xa8e9`
- name: `Microsoft.Crm.Asynchronous.TransactionLogShrinkCheckJob::CreatePriorityScheduler`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xa8a0`
- `0xa970`
- `0xf8c0`
- `0xf8e0`

## pseudocode

```c

```

## disassembly

```asm
0xa8a0  newobj   instance void <>c__DisplayClass7_0::.ctor()
0xa8a5  stloc.0
0xa8a6  ldloc.0
0xa8a7  ldarg.1
0xa8a8  stfld    string <>c__DisplayClass7_0::jobSqlServer
0xa8ad  ldarg.1
0xa8ae  call     int32 Microsoft.Crm.Asynchronous.TransactionLogShrinkConfiguration::get_DegreeOfParallelism()
0xa8b3  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction, string> <>c::<>9__7_0
0xa8b8  dup
0xa8b9  brtrue.s loc_A8D2
0xa8bb  pop
0xa8bc  ldsfld   class <>c <>c::<>9
0xa8c1  ldftn    instance string <>c::<CreatePriorityScheduler>b__7_0(class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction x)
0xa8c7  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction, string>::.ctor(object, native int)
0xa8cc  dup
0xa8cd  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction, string> <>c::<>9__7_0
0xa8d2  newobj   instance void TransactionLogDataAndDriveUsageComparer::.ctor()
0xa8d7  ldloc.0
0xa8d8  ldftn    instance void <>c__DisplayClass7_0::<CreatePriorityScheduler>b__1(class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction y)
0xa8de  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction>::.ctor(object, native int)
0xa8e3  newobj   instance void class Microsoft.Crm.Asynchronous.PriorityScheduler`2<string, class Microsoft.Crm.Asynchronous.TransactionLogDataAndDriveUsageAction>::.ctor(string, int32, class [mscorlib]System.Func`2<var<u1>, void>, var<u1>, !!T0)
0xa8e8  ret
```
