# Microsoft.Crm.Sandbox.InternalSandboxEntityDataSourceRetrieverService::<InternalRetrieveEntityDataSource>b__5_0

- ea: `0x4990`
- end: `0x49a7`
- name: `Microsoft.Crm.Sandbox.InternalSandboxEntityDataSourceRetrieverService::<InternalRetrieveEntityDataSource>b__5_0`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x4990  ldarg.1
0x4991  callvirt instance var<u1> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_Proxy()
0x4996  ldarg.0
0x4997  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallbackService::callInfo
0x499c  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo)
0x49a1  callvirt instance unsigned int8[] [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener::RetrieveEntityDataSource(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo)
0x49a6  ret
```
