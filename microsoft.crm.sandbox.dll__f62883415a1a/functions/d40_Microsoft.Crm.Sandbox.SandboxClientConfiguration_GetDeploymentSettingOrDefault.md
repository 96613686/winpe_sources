# Microsoft.Crm.Sandbox.SandboxClientConfiguration::GetDeploymentSettingOrDefault

- ea: `0xd40`
- end: `0xd6e`
- name: `Microsoft.Crm.Sandbox.SandboxClientConfiguration::GetDeploymentSettingOrDefault`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3b60`

## pseudocode

```c

```

## disassembly

```asm
0xd40  ldc.i4.1
0xd41  stloc.0
0xd42  ldloca.s 0
0xd44  constrained. Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0xd4a  callvirt instance string [mscorlib]System.Object::ToString()
0xd4f  ldarga.s 0
0xd51  constrained. Microsoft.Crm.Sandbox.SandboxClientProperty
0xd57  callvirt instance string [mscorlib]System.Object::ToString()
0xd5c  call     string [mscorlib]System.String::Concat(string, string)
0xd61  ldsfld   int32[] Microsoft.Crm.Sandbox.SandboxPropertyDefaultValues::SandboxClientPropertyDefaults
0xd66  ldarg.0
0xd67  ldelem.i4
0xd68  call     int32 Microsoft.Crm.Sandbox.SandboxConfiguration::GetDeploymentSettingOrDefault(string propertyName, int32 defaultValue)
0xd6d  ret
```
