# Microsoft.Crm.Asynchronous.BulkDeleteOperation::InternalExecute

- ea: `0x16b0`
- end: `0x16e0`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::InternalExecute`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1f340`

## pseudocode

```c

```

## disassembly

```asm
0x16b0  newobj   instance void <>c__DisplayClass15_0::.ctor()
0x16b5  stloc.0
0x16b6  ldloc.0
0x16b7  ldarg.0
0x16b8  stfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass15_0::<>4__this
0x16bd  ldloc.0
0x16be  ldarg.1
0x16bf  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass15_0::asyncEvent
0x16c4  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.BulkDeleteOperation::Logger
0x16c9  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Asynchronous.BulkDeleteServiceBulkDeleteActivity>::get_Instance()
0x16ce  ldloc.0
0x16cf  ldftn    instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult <>c__DisplayClass15_0::<InternalExecute>b__0()
0x16d5  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncHandlerResult>::.ctor(object, native int)
0x16da  call     T0x2B000001
0x16df  ret
```
