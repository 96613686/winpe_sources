# <>c__DisplayClass1_0::<StartProcessingPluginTraceLogQueues>b__0

- ea: `0x9370`
- end: `0x9387`
- name: `<>c__DisplayClass1_0::<StartProcessingPluginTraceLogQueues>b__0`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x67a0`

## pseudocode

```c

```

## disassembly

```asm
0x9370  ldarg.0
0x9371  ldfld    class Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor <>c__DisplayClass1_0::<>4__this
0x9376  ldarg.0
0x9377  ldfld    class [mscorlib]System.Threading.CancellationTokenSource <>c__DisplayClass1_0::cts
0x937c  callvirt instance valuetype [mscorlib]System.Threading.CancellationToken [mscorlib]System.Threading.CancellationTokenSource::get_Token()
0x9381  call     instance void Microsoft.Crm.Sandbox.PluginTraceLogQueuesProcessor::WritePluginTraceLogRecords(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x9386  ret
```
