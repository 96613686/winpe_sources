# Microsoft.Crm.Sandbox.LocalConfigStoreProvider::<GetAllData>b__1_0

- ea: `0x960`
- end: `0x977`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreProvider::<GetAllData>b__1_0`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x960  ldarg.1
0x961  callvirt instance var<u1> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener>::get_Proxy()
0x966  ldarg.0
0x967  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallbackService::callInfo
0x96c  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::.ctor(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo)
0x971  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxSdkListener::GetConfigStoreAllData(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo)
0x976  ret
```
