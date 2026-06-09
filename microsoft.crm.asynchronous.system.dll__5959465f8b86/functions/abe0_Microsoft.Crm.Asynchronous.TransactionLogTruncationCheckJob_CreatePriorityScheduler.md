# Microsoft.Crm.Asynchronous.TransactionLogTruncationCheckJob::CreatePriorityScheduler

- ea: `0xabe0`
- end: `0xac29`
- name: `Microsoft.Crm.Asynchronous.TransactionLogTruncationCheckJob::CreatePriorityScheduler`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0xab20`
- `0xabe0`
- `0xf980`
- `0xf9a0`

## pseudocode

```c

```

## disassembly

```asm
0xabe0  newobj   instance void <>c__DisplayClass7_0::.ctor()
0xabe5  stloc.0
0xabe6  ldloc.0
0xabe7  ldarg.1
0xabe8  stfld    string <>c__DisplayClass7_0::jobSqlServer
0xabed  ldarg.1
0xabee  call     int32 Microsoft.Crm.Asynchronous.TransactionLogTruncationConfiguration::get_DegreeOfParallelism()
0xabf3  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.TransactionLogData, string> <>c::<>9__7_0
0xabf8  dup
0xabf9  brtrue.s loc_AC12
0xabfb  pop
0xabfc  ldsfld   class <>c <>c::<>9
0xac01  ldftn    instance string <>c::<CreatePriorityScheduler>b__7_0(class Microsoft.Crm.Asynchronous.TransactionLogData x)
0xac07  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.TransactionLogData, string>::.ctor(object, native int)
0xac0c  dup
0xac0d  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.TransactionLogData, string> <>c::<>9__7_0
0xac12  newobj   instance void TransactionLogDataComparer::.ctor()
0xac17  ldloc.0
0xac18  ldftn    instance void <>c__DisplayClass7_0::<CreatePriorityScheduler>b__1(class Microsoft.Crm.Asynchronous.TransactionLogData y)
0xac1e  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.Crm.Asynchronous.TransactionLogData>::.ctor(object, native int)
0xac23  newobj   instance void class Microsoft.Crm.Asynchronous.PriorityScheduler`2<string, class Microsoft.Crm.Asynchronous.TransactionLogData>::.ctor(string, int32, class [mscorlib]System.Func`2<var<u1>, void>, var<u1>, !!T0)
0xac28  ret
```
