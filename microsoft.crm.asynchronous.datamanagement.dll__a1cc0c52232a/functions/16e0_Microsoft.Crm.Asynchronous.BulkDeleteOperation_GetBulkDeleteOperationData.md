# Microsoft.Crm.Asynchronous.BulkDeleteOperation::GetBulkDeleteOperationData

- ea: `0x16e0`
- end: `0x1710`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::GetBulkDeleteOperationData`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1f350`

## callees

- `0x1fa80`

## pseudocode

```c

```

## disassembly

```asm
0x16e0  newobj   instance void <>c__DisplayClass16_0::.ctor()
0x16e5  stloc.0
0x16e6  ldloc.0
0x16e7  ldarg.0
0x16e8  stfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass16_0::<>4__this
0x16ed  ldloc.0
0x16ee  ldarg.1
0x16ef  stfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent <>c__DisplayClass16_0::asyncEvent
0x16f4  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.BulkDeleteOperation::Logger
0x16f9  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Asynchronous.BulkDeleteGetBulkDeleteOperationDataActivity>::get_Instance()
0x16fe  ldloc.0
0x16ff  ldftn    instance class [Microsoft.Crm]Microsoft.Crm.BulkDeleteData <>c__DisplayClass16_0::<GetBulkDeleteOperationData>b__0()
0x1705  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Crm]Microsoft.Crm.BulkDeleteData>::.ctor(object, native int)
0x170a  call     T0x2B000002
0x170f  ret
```
