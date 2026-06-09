# Microsoft.Crm.Asynchronous.TransactionLogBackupCheckJob::CreatePriorityScheduler

- ea: `0xaf80`
- end: `0xafbc`
- name: `Microsoft.Crm.Asynchronous.TransactionLogBackupCheckJob::CreatePriorityScheduler`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xae20`
- `0xaf80`
- `0xfa60`

## pseudocode

```c

```

## disassembly

```asm
0xaf80  ldarg.1
0xaf81  call     int32 Microsoft.Crm.Asynchronous.TransactionLogBackupConfiguration::get_DegreeOfParallelism()
0xaf86  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.TransactionLogBackupData, string> <>c::<>9__8_0
0xaf8b  dup
0xaf8c  brtrue.s loc_AFA5
0xaf8e  pop
0xaf8f  ldsfld   class <>c <>c::<>9
0xaf94  ldftn    instance string <>c::<CreatePriorityScheduler>b__8_0(class Microsoft.Crm.Asynchronous.TransactionLogBackupData x)
0xaf9a  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.TransactionLogBackupData, string>::.ctor(object, native int)
0xaf9f  dup
0xafa0  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.TransactionLogBackupData, string> <>c::<>9__8_0
0xafa5  newobj   instance void TransactionLogBackupDataComparer::.ctor()
0xafaa  ldarg.0
0xafab  ldftn    instance void Microsoft.Crm.Asynchronous.TransactionLogBackupCheckJob::<CreatePriorityScheduler>b__8_1(class Microsoft.Crm.Asynchronous.TransactionLogBackupData y)
0xafb1  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.Crm.Asynchronous.TransactionLogBackupData>::.ctor(object, native int)
0xafb6  newobj   instance void class Microsoft.Crm.Asynchronous.PriorityScheduler`2<string, class Microsoft.Crm.Asynchronous.TransactionLogBackupData>::.ctor(string, int32, class [mscorlib]System.Func`2<var<u1>, void>, var<u1>, !!T0)
0xafbb  ret
```
