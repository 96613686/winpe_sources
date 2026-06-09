# Microsoft.Crm.Asynchronous.Rollups.Bootstrap.MarkCompletion::ExecuteInternal

- ea: `0xfd20`
- end: `0xfd3e`
- name: `Microsoft.Crm.Asynchronous.Rollups.Bootstrap.MarkCompletion::ExecuteInternal`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xbf80`
- `0xf7c0`
- `0x100e0`

## pseudocode

```c

```

## disassembly

```asm
0xfd20  ldarg.0
0xfd21  call     instance class Microsoft.Crm.Asynchronous.IBootstrapRollupOperation Microsoft.Crm.Asynchronous.Rollups.Bootstrap.BootstrapStep::get_Process()
0xfd26  callvirt instance class Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess Microsoft.Crm.Asynchronous.IBootstrapRollupOperation::get_DataAccess()
0xfd2b  ldarg.0
0xfd2c  ldftn    instance void Microsoft.Crm.Asynchronous.Rollups.Bootstrap.MarkCompletion::<ExecuteInternal>b__1_0()
0xfd32  newobj   instance void [mscorlib]System.Action::.ctor(object, native int)
0xfd37  callvirt instance void Microsoft.Crm.Asynchronous.Rollups.IBootstrapDataAccess::ProcessJobCompletion(class [mscorlib]System.Action action)
0xfd3c  ldc.i4.m1
0xfd3d  ret
```
