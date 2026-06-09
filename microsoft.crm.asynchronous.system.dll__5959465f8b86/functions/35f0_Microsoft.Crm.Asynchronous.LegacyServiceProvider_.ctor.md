# Microsoft.Crm.Asynchronous.LegacyServiceProvider::.ctor

- ea: `0x35f0`
- end: `0x361f`
- name: `Microsoft.Crm.Asynchronous.LegacyServiceProvider::.ctor`
- size: `47`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3520`

## pseudocode

```c

```

## disassembly

```asm
0x35f0  ldarg.0
0x35f1  call     instance void [mscorlib]System.Object::.ctor()
0x35f6  ldarg.0
0x35f7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::.ctor()
0x35fc  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> Microsoft.Crm.Asynchronous.LegacyServiceProvider::_serviceProviderLookUp
0x3601  ldarg.0
0x3602  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> Microsoft.Crm.Asynchronous.LegacyServiceProvider::_serviceProviderLookUp
0x3607  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.IIsolatablePluginExecutionContext
0x360c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3611  ldarg.1
0x3612  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::Add(var<u1>, !!T0)
0x3617  ldarg.0
0x3618  ldarg.1
0x3619  stfld    class [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.V5AsyncExecutionContext Microsoft.Crm.Asynchronous.LegacyServiceProvider::_context
0x361e  ret
```
