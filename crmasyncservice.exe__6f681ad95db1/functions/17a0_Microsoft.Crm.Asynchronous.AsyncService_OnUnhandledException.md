# Microsoft.Crm.Asynchronous.AsyncService::OnUnhandledException

- ea: `0x17a0`
- end: `0x182e`
- name: `Microsoft.Crm.Asynchronous.AsyncService::OnUnhandledException`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x17a0`
- `0x5200`
- `0xa610`

## pseudocode

```c

```

## disassembly

```asm
0x17a0  newobj   instance void <>c__DisplayClass48_0::.ctor()
0x17a5  dup
0x17a6  ldarg.0
0x17a7  stfld    class Microsoft.Crm.Asynchronous.AsyncService <>c__DisplayClass48_0::<>4__this
0x17ac  dup
0x17ad  ldarg.2
0x17ae  stfld    class [mscorlib]System.UnhandledExceptionEventArgs <>c__DisplayClass48_0::e
0x17b3  dup
0x17b4  ldftn    instance void <>c__DisplayClass48_0::<OnUnhandledException>b__0()
0x17ba  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x17bf  call     void Microsoft.Crm.Asynchronous.ShutdownSequenceFailSafeOperation::Execute(class [mscorlib]System.Action operation)
0x17c4  dup
0x17c5  ldftn    instance void <>c__DisplayClass48_0::<OnUnhandledException>b__1()
0x17cb  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x17d0  call     void Microsoft.Crm.Asynchronous.ShutdownSequenceFailSafeOperation::Execute(class [mscorlib]System.Action operation)
0x17d5  ldftn    instance void <>c__DisplayClass48_0::<OnUnhandledException>b__2()
0x17db  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x17e0  call     void Microsoft.Crm.Asynchronous.ShutdownSequenceFailSafeOperation::Execute(class [mscorlib]System.Action operation)
0x17e5  ldsfld   class [mscorlib]System.Action <>c::<>9__48_3
0x17ea  dup
0x17eb  brtrue.s loc_1804
0x17ed  pop
0x17ee  ldsfld   class <>c <>c::<>9
0x17f3  ldftn    instance void <>c::<OnUnhandledException>b__48_3()
0x17f9  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x17fe  dup
0x17ff  stsfld   class [mscorlib]System.Action <>c::<>9__48_3
0x1804  call     void Microsoft.Crm.Asynchronous.ShutdownSequenceFailSafeOperation::Execute(class [mscorlib]System.Action operation)
0x1809  ldsfld   class [mscorlib]System.Action <>c::<>9__48_4
0x180e  dup
0x180f  brtrue.s loc_1828
0x1811  pop
0x1812  ldsfld   class <>c <>c::<>9
0x1817  ldftn    instance void <>c::<OnUnhandledException>b__48_4()
0x181d  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0x1822  dup
0x1823  stsfld   class [mscorlib]System.Action <>c::<>9__48_4
0x1828  call     void Microsoft.Crm.Asynchronous.ShutdownSequenceFailSafeOperation::Execute(class [mscorlib]System.Action operation)
0x182d  ret
```
