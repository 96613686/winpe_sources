# Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::GetDeploymentSettingOrDefault

- ea: `0x8060`
- end: `0x808e`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerConfiguration::GetDeploymentSettingOrDefault`
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
0x8060  ldc.i4.3
0x8061  stloc.0
0x8062  ldloca.s 0
0x8064  constrained. Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x806a  callvirt instance string [mscorlib]System.Object::ToString()
0x806f  ldarga.s 0
0x8071  constrained. Microsoft.Crm.Sandbox.SandboxWorkerProperty
0x8077  callvirt instance string [mscorlib]System.Object::ToString()
0x807c  call     string [mscorlib]System.String::Concat(string, string)
0x8081  ldsfld   int32[] Microsoft.Crm.Sandbox.SandboxPropertyDefaultValues::SandboxWorkerPropertyDefaults
0x8086  ldarg.0
0x8087  ldelem.i4
0x8088  call     int32 Microsoft.Crm.Sandbox.SandboxConfiguration::GetDeploymentSettingOrDefault(string propertyName, int32 defaultValue)
0x808d  ret
```
