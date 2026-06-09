# Microsoft.Crm.Asynchronous.Rollups.RollupJob::Delete

- ea: `0xdf60`
- end: `0xdf73`
- name: `Microsoft.Crm.Asynchronous.Rollups.RollupJob::Delete`
- size: `19`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0xcc50`
- `0xcdd0`
- `0xce30`
- `0xd880`
- `0xdf80`
- `0xdfe0`

## callees

- `0xe6a0`

## pseudocode

```c

```

## disassembly

```asm
0xdf60  ldc.i4.3
0xdf61  ldarg.0
0xdf62  ldftn    instance valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.RollupJob::<Delete>b__56_0()
0xdf68  newobj   instance void class [mscorlib]System.Func`1<valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult>::.ctor(object, native int)
0xdf6d  call     valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult Microsoft.Crm.Asynchronous.Rollups.RollupsDataAccess::RetryOnDeadlock(int32 tryCount, class [mscorlib]System.Func`1<valuetype Microsoft.Crm.Asynchronous.Rollups.SqlCommandResult> function)
0xdf72  ret
```
