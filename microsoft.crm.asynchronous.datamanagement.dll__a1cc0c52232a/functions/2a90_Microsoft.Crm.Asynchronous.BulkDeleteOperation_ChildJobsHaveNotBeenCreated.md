# Microsoft.Crm.Asynchronous.BulkDeleteOperation::ChildJobsHaveNotBeenCreated

- ea: `0x2a90`
- end: `0x2aac`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::ChildJobsHaveNotBeenCreated`
- size: `28`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1f350`

## pseudocode

```c

```

## disassembly

```asm
0x2a90  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.BulkDeleteOperation::Logger
0x2a95  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Asynchronous.BulkDeleteChildJobsHaveNotBeenCreatedActivity>::get_Instance()
0x2a9a  ldarg.0
0x2a9b  ldftn    instance bool Microsoft.Crm.Asynchronous.BulkDeleteOperation::<ChildJobsHaveNotBeenCreated>b__34_0()
0x2aa1  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x2aa6  call     T0x2B000003
0x2aab  ret
```
