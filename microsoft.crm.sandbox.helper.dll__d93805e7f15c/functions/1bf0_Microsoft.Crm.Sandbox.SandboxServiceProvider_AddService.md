# Microsoft.Crm.Sandbox.SandboxServiceProvider::AddService

- ea: `0x1bf0`
- end: `0x1bfe`
- name: `Microsoft.Crm.Sandbox.SandboxServiceProvider::AddService`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x1bf0  ldarg.0
0x1bf1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object> Microsoft.Crm.Sandbox.SandboxServiceProvider::_serviceProviderLookUp
0x1bf6  ldarg.1
0x1bf7  ldarg.2
0x1bf8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Type, object>::Add(var<u1>, !!T0)
0x1bfd  ret
```
