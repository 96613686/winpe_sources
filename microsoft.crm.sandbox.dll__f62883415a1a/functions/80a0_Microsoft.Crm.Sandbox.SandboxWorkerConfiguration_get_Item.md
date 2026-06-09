# Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::get_Item

- ea: `0x80a0`
- end: `0x80d0`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::get_Item`
- size: `48`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x620`
- `0x4e30`
- `0x9e70`

## callees

- `0x3a70`

## pseudocode

```c

```

## disassembly

```asm
0x80a0  ldarg.0
0x80a1  ldarg.1
0x80a2  ldc.i4.3
0x80a3  stloc.0
0x80a4  ldloca.s 0
0x80a6  constrained. Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x80ac  callvirt instance string [mscorlib]System.Object::ToString()
0x80b1  ldarga.s 1
0x80b3  constrained. Microsoft.Crm.Sandbox.SandboxWorkerProperty
0x80b9  callvirt instance string [mscorlib]System.Object::ToString()
0x80be  call     string [mscorlib]System.String::Concat(string, string)
0x80c3  ldsfld   int32[] Microsoft.Crm.Sandbox.SandboxPropertyDefaultValues::SandboxWorkerPropertyDefaults
0x80c8  ldarg.1
0x80c9  ldelem.i4
0x80ca  call     instance int32 Microsoft.Crm.Sandbox.SandboxConfiguration::GetPropertyValue(int32 key, string propertyName, int32 defaultValue)
0x80cf  ret
```
