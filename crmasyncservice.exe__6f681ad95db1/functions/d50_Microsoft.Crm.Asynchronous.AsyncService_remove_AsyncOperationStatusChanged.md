# Microsoft.Crm.Asynchronous.AsyncService::remove_AsyncOperationStatusChanged

- ea: `0xd50`
- end: `0xd79`
- name: `Microsoft.Crm.Asynchronous.AsyncService::remove_AsyncOperationStatusChanged`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xd50`

## pseudocode

```c

```

## disassembly

```asm
0xd50  ldarg.0
0xd51  ldfld    class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationStatusChangedEventArgs> Microsoft.Crm.Asynchronous.AsyncService::AsyncOperationStatusChanged
0xd56  stloc.0
0xd57  ldloc.0
0xd58  stloc.1
0xd59  ldloc.1
0xd5a  ldarg.1
0xd5b  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Remove(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0xd60  castclass class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationStatusChangedEventArgs>
0xd65  stloc.2
0xd66  ldarg.0
0xd67  ldflda   class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationStatusChangedEventArgs> Microsoft.Crm.Asynchronous.AsyncService::AsyncOperationStatusChanged
0xd6c  ldloc.2
0xd6d  ldloc.1
0xd6e  call     T0x2B000002
0xd73  stloc.0
0xd74  ldloc.0
0xd75  ldloc.1
0xd76  bne.un.s loc_D57
0xd78  ret
```
