# Microsoft.Crm.Extensibility.PluginAssemblyFactory::get_BinFolder

- ea: `0x410d0`
- end: `0x4111a`
- name: `Microsoft.Crm.Extensibility.PluginAssemblyFactory::get_BinFolder`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1e3c0`

## callees

- `0x410d0`

## string_xrefs

- `0x410e4`: `CRM_Client_InstallDir`
- `0x410fc`: `CRM_Server_InstallDir`

## pseudocode

```c

```

## disassembly

```asm
0x410d0  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInCrmInternalToolContext()
0x410d5  brfalse.s loc_410DD
0x410d7  call     string [mscorlib]System.Environment::get_CurrentDirectory()
0x410dc  ret
0x410dd  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x410e2  brfalse.s loc_410FC
0x410e4  ldstr    aCrmClientInsta// "CRM_Client_InstallDir"
0x410e9  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x410ee  castclass [mscorlib]System.String
0x410f3  stloc.0
0x410f4  ldstr    aClientBin// "client\\bin\\"
0x410f9  stloc.1
0x410fa  br.s     loc_41112
0x410fc  ldstr    aCrmServerInsta// "CRM_Server_InstallDir"
0x41101  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x41106  castclass [mscorlib]System.String
0x4110b  stloc.0
0x4110c  ldstr    aServerBin// "server\\bin\\"
0x41111  stloc.1
0x41112  ldloc.0
0x41113  ldloc.1
0x41114  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x41119  ret
```
