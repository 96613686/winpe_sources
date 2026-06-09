# Microsoft.Crm.Sandbox.SandboxEntityDataSourceRetrieverService::RetrieveEntityDataSource

- ea: `0xa170`
- end: `0xa182`
- name: `Microsoft.Crm.Sandbox.SandboxEntityDataSourceRetrieverService::RetrieveEntityDataSource`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0xa1a0`

## pseudocode

```c

```

## disassembly

```asm
0xa170  ldarg.0
0xa171  ldfld    class Microsoft.Crm.Sandbox.IInternalDataSourceRetrieverService Microsoft.Crm.Sandbox.SandboxEntityDataSourceRetrieverService::_internalService
0xa176  callvirt instance unsigned int8[] Microsoft.Crm.Sandbox.IInternalDataSourceRetrieverService::WrapperRetrieveEntityDataSource()
0xa17b  ldnull
0xa17c  call     T0x2B00001F
0xa181  ret
```
