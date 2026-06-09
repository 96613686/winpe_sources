# Microsoft.Crm.ThreadPoolWrapper::QueueUserWorkItem

- ea: `0x320`
- end: `0x33d`
- name: `Microsoft.Crm.ThreadPoolWrapper::QueueUserWorkItem`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x320`

## pseudocode

```c

```

## disassembly

```asm
0x320  ldsfld   class [mscorlib]System.Action`2<class [mscorlib]System.Threading.WaitCallback, object> Microsoft.Crm.ThreadPoolWrapper::_queueOverride
0x325  brfalse.s loc_334
0x327  ldsfld   class [mscorlib]System.Action`2<class [mscorlib]System.Threading.WaitCallback, object> Microsoft.Crm.ThreadPoolWrapper::_queueOverride
0x32c  ldarg.0
0x32d  ldarg.1
0x32e  callvirt instance void class [mscorlib]System.Action`2<class [mscorlib]System.Threading.WaitCallback, object>::Invoke(var<u1>, !!T0)
0x333  ret
0x334  ldarg.0
0x335  ldarg.1
0x336  call     bool [mscorlib]System.Threading.ThreadPool::QueueUserWorkItem(class [mscorlib]System.Threading.WaitCallback, object)
0x33b  pop
0x33c  ret
```
