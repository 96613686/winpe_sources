# Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item

- ea: `0x5530`
- end: `0x5560`
- name: `Microsoft.Crm.Sandbox.SandboxHostConfiguration::get_Item`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3f00`

## callees

- `0x3a70`

## pseudocode

```c

```

## disassembly

```asm
0x5530  ldarg.0
0x5531  ldarg.1
0x5532  ldc.i4.2
0x5533  stloc.0
0x5534  ldloca.s 0
0x5536  constrained. Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x553c  callvirt instance string [mscorlib]System.Object::ToString()
0x5541  ldarga.s 1
0x5543  constrained. Microsoft.Crm.Sandbox.SandboxHostProperty
0x5549  callvirt instance string [mscorlib]System.Object::ToString()
0x554e  call     string [mscorlib]System.String::Concat(string, string)
0x5553  ldsfld   int32[] Microsoft.Crm.Sandbox.SandboxPropertyDefaultValues::SandboxHostPropertyDefaults
0x5558  ldarg.1
0x5559  ldelem.i4
0x555a  call     instance int32 Microsoft.Crm.Sandbox.SandboxConfiguration::GetPropertyValue(int32 key, string propertyName, int32 defaultValue)
0x555f  ret
```
