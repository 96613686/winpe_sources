# Microsoft.Crm.Sandbox.SandboxHostConfiguration::GetDeploymentSettingOrDefault

- ea: `0x54f0`
- end: `0x551e`
- name: `Microsoft.Crm.Sandbox.SandboxHostConfiguration::GetDeploymentSettingOrDefault`
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
0x54f0  ldc.i4.2
0x54f1  stloc.0
0x54f2  ldloca.s 0
0x54f4  constrained. Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x54fa  callvirt instance string [mscorlib]System.Object::ToString()
0x54ff  ldarga.s 0
0x5501  constrained. Microsoft.Crm.Sandbox.SandboxHostProperty
0x5507  callvirt instance string [mscorlib]System.Object::ToString()
0x550c  call     string [mscorlib]System.String::Concat(string, string)
0x5511  ldsfld   int32[] Microsoft.Crm.Sandbox.SandboxPropertyDefaultValues::SandboxHostPropertyDefaults
0x5516  ldarg.0
0x5517  ldelem.i4
0x5518  call     int32 Microsoft.Crm.Sandbox.SandboxConfiguration::GetDeploymentSettingOrDefault(string propertyName, int32 defaultValue)
0x551d  ret
```
