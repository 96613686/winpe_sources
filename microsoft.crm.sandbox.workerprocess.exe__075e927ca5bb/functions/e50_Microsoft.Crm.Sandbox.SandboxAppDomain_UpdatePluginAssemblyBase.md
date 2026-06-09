# Microsoft.Crm.Sandbox.SandboxAppDomain::UpdatePluginAssemblyBase

- ea: `0xe50`
- end: `0xea5`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomain::UpdatePluginAssemblyBase`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0xdf0`
- `0xe30`

## callees

- `0xe50`

## string_xrefs

- `0xe63`: `AssemblyCache`

## pseudocode

```c

```

## disassembly

```asm
0xe50  ldnull
0xe51  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::AssemblyCachePath(string)
0xe56  call     bool [mscorlib]System.IO.Directory::Exists(string)
0xe5b  brtrue.s loc_E83
0xe5d  ldarg.0
0xe5e  ldstr    aCMscrmRo// "C:\\MSCRM_RO\\"
0xe63  ldstr    aAssemblycache// "AssemblyCache"
0xe68  ldarg.0
0xe69  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::_organizationId
0xe6e  ldstr    aB// "B"
0xe73  call     instance string [mscorlib]System.Guid::ToString(string)
0xe78  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0xe7d  stfld    string Microsoft.Crm.Sandbox.SandboxAppDomain::_pluginAssemblyBase
0xe82  ret
0xe83  ldarg.0
0xe84  ldnull
0xe85  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::AssemblyCachePath(string)
0xe8a  ldarg.0
0xe8b  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::_organizationId
0xe90  ldstr    aB// "B"
0xe95  call     instance string [mscorlib]System.Guid::ToString(string)
0xe9a  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xe9f  stfld    string Microsoft.Crm.Sandbox.SandboxAppDomain::_pluginAssemblyBase
0xea4  ret
```
