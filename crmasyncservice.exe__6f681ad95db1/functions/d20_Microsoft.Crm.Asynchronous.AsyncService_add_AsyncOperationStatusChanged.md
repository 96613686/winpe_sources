# Microsoft.Crm.Asynchronous.AsyncService::add_AsyncOperationStatusChanged

- ea: `0xd20`
- end: `0xd49`
- name: `Microsoft.Crm.Asynchronous.AsyncService::add_AsyncOperationStatusChanged`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xd20`

## pseudocode

```c

```

## disassembly

```asm
0xd20  ldarg.0
0xd21  ldfld    class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationStatusChangedEventArgs> Microsoft.Crm.Asynchronous.AsyncService::AsyncOperationStatusChanged
0xd26  stloc.0
0xd27  ldloc.0
0xd28  stloc.1
0xd29  ldloc.1
0xd2a  ldarg.1
0xd2b  call     class [mscorlib]System.Delegate [mscorlib]System.Delegate::Combine(class [mscorlib]System.Delegate, class [mscorlib]System.Delegate)
0xd30  castclass class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationStatusChangedEventArgs>
0xd35  stloc.2
0xd36  ldarg.0
0xd37  ldflda   class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncOperationStatusChangedEventArgs> Microsoft.Crm.Asynchronous.AsyncService::AsyncOperationStatusChanged
0xd3c  ldloc.2
0xd3d  ldloc.1
0xd3e  call     T0x2B000002
0xd43  stloc.0
0xd44  ldloc.0
0xd45  ldloc.1
0xd46  bne.un.s loc_D27
0xd48  ret
```
