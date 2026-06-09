# Microsoft.Crm.Sandbox.SandboxServiceProvider::.ctor_0

- ea: `0x1ba0`
- end: `0x1be1`
- name: `Microsoft.Crm.Sandbox.SandboxServiceProvider::.ctor_0`
- size: `65`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x7b0`
- `0x1240`

## callees

- `0x1ba0`
- `0x1de0`

## string_xrefs

- `0x1bb4`: `services`

## pseudocode

```c

```

## disassembly

```asm
0x1ba0  ldarg.0
0x1ba1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::.ctor()
0x1ba6  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> Microsoft.Crm.Sandbox.SandboxServiceProvider::_serviceProviderLookUp
0x1bab  ldarg.0
0x1bac  call     instance void [mscorlib]System.Object::.ctor()
0x1bb1  ldarg.1
0x1bb2  brtrue.s loc_1BBF
0x1bb4  ldstr    aServices// "services"
0x1bb9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1bbe  throw
0x1bbf  ldarg.0
0x1bc0  ldarg.1
0x1bc1  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> Microsoft.Crm.Sandbox.SandboxServiceProvider::_serviceProviderLookUp
0x1bc6  ldarg.0
0x1bc7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> Microsoft.Crm.Sandbox.SandboxServiceProvider::_serviceProviderLookUp
0x1bcc  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ITracingService
0x1bd1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1bd6  newobj   instance void Microsoft.Crm.Sandbox.SandboxTracingService::.ctor()
0x1bdb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::Add(var<u1>, !!T0)
0x1be0  ret
```
