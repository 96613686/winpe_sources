# Microsoft.Crm.Sandbox.SandboxConfiguration::set_Item

- ea: `0x3a50`
- end: `0x3a5e`
- name: `Microsoft.Crm.Sandbox.SandboxConfiguration::set_Item`
- size: `14`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd70`
- `0x5520`
- `0x8090`

## pseudocode

```c

```

## disassembly

```asm
0x3a50  ldarg.0
0x3a51  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Sandbox.SandboxConfiguration::_dictionary
0x3a56  ldarg.1
0x3a57  ldarg.2
0x3a58  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::set_Item(var<u1>, !!T0)
0x3a5d  ret
```
