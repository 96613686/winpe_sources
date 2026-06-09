# Microsoft.Crm.Sandbox.SandboxConfiguration::GetDeploymentSettingOrDefault

- ea: `0x3b60`
- end: `0x3b90`
- name: `Microsoft.Crm.Sandbox.SandboxConfiguration::GetDeploymentSettingOrDefault`
- size: `48`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xd40`
- `0x54f0`
- `0x8060`

## callees

- `0x3b60`

## string_xrefs

- `0x3b68`: `LocatorService.Instance is null`

## pseudocode

```c

```

## disassembly

```asm
0x3b60  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x3b65  ldnull
0x3b66  cgt.un
0x3b68  ldstr    aLocatorservice// "LocatorService.Instance is null"
0x3b6d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x3b72  ldarg.1
0x3b73  stloc.0
0x3b74  ldarg.0
0x3b75  ldnull
0x3b76  call     T0x2B000006
0x3b7b  stloc.1
0x3b7c  ldloc.1
0x3b7d  brfalse.s loc_3B8E
0x3b7f  ldloc.1
0x3b80  isinst   [mscorlib]System.Int32
0x3b85  brfalse.s loc_3B8E
0x3b87  ldloc.1
0x3b88  unbox.any [mscorlib]System.Int32
0x3b8d  stloc.0
0x3b8e  ldloc.0
0x3b8f  ret
```
