# Microsoft.Crm.Sandbox.SandboxClientConfiguration::get_Item

- ea: `0xd80`
- end: `0xdb0`
- name: `Microsoft.Crm.Sandbox.SandboxClientConfiguration::get_Item`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3a70`

## pseudocode

```c

```

## disassembly

```asm
0xd80  ldarg.0
0xd81  ldarg.1
0xd82  ldc.i4.1
0xd83  stloc.0
0xd84  ldloca.s 0
0xd86  constrained. Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0xd8c  callvirt instance string [mscorlib]System.Object::ToString()
0xd91  ldarga.s 1
0xd93  constrained. Microsoft.Crm.Sandbox.SandboxClientProperty
0xd99  callvirt instance string [mscorlib]System.Object::ToString()
0xd9e  call     string [mscorlib]System.String::Concat(string, string)
0xda3  ldsfld   int32[] Microsoft.Crm.Sandbox.SandboxPropertyDefaultValues::SandboxClientPropertyDefaults
0xda8  ldarg.1
0xda9  ldelem.i4
0xdaa  call     instance int32 Microsoft.Crm.Sandbox.SandboxConfiguration::GetPropertyValue(int32 key, string propertyName, int32 defaultValue)
0xdaf  ret
```
