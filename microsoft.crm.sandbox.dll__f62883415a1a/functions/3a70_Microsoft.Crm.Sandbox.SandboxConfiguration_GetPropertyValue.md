# Microsoft.Crm.Sandbox.SandboxConfiguration::GetPropertyValue

- ea: `0x3a70`
- end: `0x3ab0`
- name: `Microsoft.Crm.Sandbox.SandboxConfiguration::GetPropertyValue`
- size: `64`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd80`
- `0x5530`
- `0x80a0`

## callees

- `0x3a70`

## pseudocode

```c

```

## disassembly

```asm
0x3a70  ldarg.2
0x3a71  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x3a76  stloc.0
0x3a77  ldloc.0
0x3a78  brfalse.s loc_3A89
0x3a7a  ldloc.0
0x3a7b  isinst   [mscorlib]System.Int32
0x3a80  brfalse.s loc_3A89
0x3a82  ldloc.0
0x3a83  unbox.any [mscorlib]System.Int32
0x3a88  ret
0x3a89  ldarg.0
0x3a8a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Sandbox.SandboxConfiguration::_dictionary
0x3a8f  ldarg.1
0x3a90  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::ContainsKey(var<u1>)
0x3a95  brfalse.s loc_3AA6
0x3a97  ldarg.0
0x3a98  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Sandbox.SandboxConfiguration::_dictionary
0x3a9d  ldarg.1
0x3a9e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::get_Item(void)
0x3aa3  stloc.1
0x3aa4  br.s     loc_3AAE
0x3aa6  ldarg.2
0x3aa7  ldarg.3
0x3aa8  call     T0x2B000011
0x3aad  stloc.1
0x3aae  ldloc.1
0x3aaf  ret
```
