# Microsoft.Crm.Asynchronous.BulkDeleteOperation::UserHasBulkDeletePrivilege

- ea: `0x17b0`
- end: `0x17e7`
- name: `Microsoft.Crm.Asynchronous.BulkDeleteOperation::UserHasBulkDeletePrivilege`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1f350`

## callees

- `0x1fb50`

## pseudocode

```c

```

## disassembly

```asm
0x17b0  newobj   instance void <>c__DisplayClass19_0::.ctor()
0x17b5  stloc.0
0x17b6  ldloc.0
0x17b7  ldarg.0
0x17b8  stfld    class Microsoft.Crm.Asynchronous.BulkDeleteOperation <>c__DisplayClass19_0::<>4__this
0x17bd  ldloc.0
0x17be  ldarg.1
0x17bf  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass19_0::userId
0x17c4  ldloc.0
0x17c5  ldarg.2
0x17c6  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass19_0::organizationId
0x17cb  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Asynchronous.BulkDeleteOperation::Logger
0x17d0  call     var<u1> class [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetrySingletonActivityType`1<class Microsoft.Crm.Asynchronous.BulkDeleteUserHasBulkDeletePrivilegeActivity>::get_Instance()
0x17d5  ldloc.0
0x17d6  ldftn    instance bool <>c__DisplayClass19_0::<UserHasBulkDeletePrivilege>b__0()
0x17dc  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x17e1  call     T0x2B000003
0x17e6  ret
```
