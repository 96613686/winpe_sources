# Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine::remove_AsyncOperationStatusChanged

- ea: `0x5020`
- end: `0x5049`
- name: `Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine::remove_AsyncOperationStatusChanged`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x5020`

## pseudocode

```c

```

## disassembly

```asm
0x5020  ldarg.0
0x5021  ldfld    class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationStatusChangedEventArgs> Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine::AsyncOperationStatusChanged
0x5026  stloc.0
0x5027  ldloc.0
0x5028  stloc.1
0x5029  ldloc.1
0x502a  ldarg.1
0x502b  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0x5030  castclass class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationStatusChangedEventArgs>
0x5035  stloc.2
0x5036  ldarg.0
0x5037  ldflda   class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationStatusChangedEventArgs> Microsoft.Crm.Asynchronous.QueueManagerExecutionEngine::AsyncOperationStatusChanged
0x503c  ldloc.2
0x503d  ldloc.1
0x503e  call     T0x2B000002
0x5043  stloc.0
0x5044  ldloc.0
0x5045  ldloc.1
0x5046  bne.un.s loc_5027
0x5048  ret
```
