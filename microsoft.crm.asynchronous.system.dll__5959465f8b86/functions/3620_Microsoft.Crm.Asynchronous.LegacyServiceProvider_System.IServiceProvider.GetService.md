# Microsoft.Crm.Asynchronous.LegacyServiceProvider::System.IServiceProvider.GetService

- ea: `0x3620`
- end: `0x3656`
- name: `Microsoft.Crm.Asynchronous.LegacyServiceProvider::System.IServiceProvider.GetService`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x3620`

## string_xrefs

- `0x3623`: `serviceType`

## pseudocode

```c

```

## disassembly

```asm
0x3620  ldnull
0x3621  stloc.0
0x3622  ldarg.1
0x3623  ldstr    aServicetype// "serviceType"
0x3628  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x362d  ldarg.0
0x362e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> Microsoft.Crm.Asynchronous.LegacyServiceProvider::_serviceProviderLookUp
0x3633  ldarg.1
0x3634  ldloca.s 0
0x3636  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::TryGetValue(var<u1>, !!T0)
0x363b  brfalse.s loc_363F
0x363d  ldloc.0
0x363e  ret
0x363f  ldarg.0
0x3640  ldfld    class [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.V5AsyncExecutionContext Microsoft.Crm.Asynchronous.LegacyServiceProvider::_context
0x3645  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext [Microsoft.Crm.Asynchronous.HandlerUtility]Microsoft.Crm.Asynchronous.LegacyAsyncExecutionContextBase::get_InnerContext()
0x364a  callvirt instance class [mscorlib]System.IServiceProvider [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_ServiceProvider()
0x364f  ldarg.1
0x3650  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x3655  ret
```
