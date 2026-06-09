# Microsoft.Crm.Sandbox.InternalSandboxEntityDataSourceRetrieverService::InternalRetrieveEntityDataSource

- ea: `0x4970`
- end: `0x4983`
- name: `Microsoft.Crm.Sandbox.InternalSandboxEntityDataSourceRetrieverService::InternalRetrieveEntityDataSource`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x4950`

## pseudocode

```c

```

## disassembly

```asm
0x4970  ldarg.0
0x4971  ldarg.0
0x4972  ldftn    instance unsigned int8[] Microsoft.Crm.Sandbox.InternalSandboxEntityDataSourceRetrieverService::<InternalRetrieveEntityDataSource>b__5_0(class Microsoft.Crm.Sandbox.SandboxSdkClient client)
0x4978  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Sandbox.SandboxSdkClient, unsigned int8[]>::.ctor(object, native int)
0x497d  call     T0x2B000004
0x4982  ret
```
