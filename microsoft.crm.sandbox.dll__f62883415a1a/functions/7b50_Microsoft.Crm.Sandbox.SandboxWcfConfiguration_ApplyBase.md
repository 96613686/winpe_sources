# Microsoft.Crm.Sandbox.SandboxWcfConfiguration::ApplyBase

- ea: `0x7b50`
- end: `0x7bed`
- name: `Microsoft.Crm.Sandbox.SandboxWcfConfiguration::ApplyBase`
- size: `157`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7bf0`
- `0x7d40`

## callees

- `0x7b50`

## pseudocode

```c

```

## disassembly

```asm
0x7b50  ldarg.0
0x7b51  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7b56  ldc.i4.5
0x7b57  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7b5c  brfalse.s loc_7B77
0x7b5e  ldarg.1
0x7b5f  ldc.i4.0
0x7b60  ldc.i4.0
0x7b61  ldarg.0
0x7b62  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7b67  ldc.i4.5
0x7b68  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7b6d  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x7b72  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_CloseTimeout(valuetype [mscorlib]System.TimeSpan)
0x7b77  ldarg.0
0x7b78  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7b7d  ldc.i4.6
0x7b7e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7b83  brfalse.s loc_7B9E
0x7b85  ldarg.1
0x7b86  ldc.i4.0
0x7b87  ldc.i4.0
0x7b88  ldarg.0
0x7b89  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7b8e  ldc.i4.6
0x7b8f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7b94  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x7b99  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_OpenTimeout(valuetype [mscorlib]System.TimeSpan)
0x7b9e  ldarg.0
0x7b9f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7ba4  ldc.i4.7
0x7ba5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7baa  brfalse.s loc_7BC5
0x7bac  ldarg.1
0x7bad  ldc.i4.0
0x7bae  ldc.i4.0
0x7baf  ldarg.0
0x7bb0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7bb5  ldc.i4.7
0x7bb6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7bbb  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x7bc0  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_ReceiveTimeout(valuetype [mscorlib]System.TimeSpan)
0x7bc5  ldarg.0
0x7bc6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7bcb  ldc.i4.8
0x7bcc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::ContainsKey(var<u1>)
0x7bd1  brfalse.s loc_7BEC
0x7bd3  ldarg.1
0x7bd4  ldc.i4.0
0x7bd5  ldc.i4.0
0x7bd6  ldarg.0
0x7bd7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32> Microsoft.Crm.Sandbox.SandboxWcfConfiguration::_registryProperties
0x7bdc  ldc.i4.8
0x7bdd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Sandbox.SandboxWcfProperty, int32>::get_Item(void)
0x7be2  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x7be7  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_SendTimeout(valuetype [mscorlib]System.TimeSpan)
0x7bec  ret
```
