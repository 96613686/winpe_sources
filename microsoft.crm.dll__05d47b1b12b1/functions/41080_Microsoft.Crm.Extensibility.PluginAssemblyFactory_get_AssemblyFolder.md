# Microsoft.Crm.Extensibility.PluginAssemblyFactory::get_AssemblyFolder

- ea: `0x41080`
- end: `0x410ca`
- name: `Microsoft.Crm.Extensibility.PluginAssemblyFactory::get_AssemblyFolder`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x40f10`
- `0x41140`

## callees

- `0x41080`

## string_xrefs

- `0x41094`: `CRM_Client_InstallDir`
- `0x410ac`: `CRM_Server_InstallDir`

## pseudocode

```c

```

## disassembly

```asm
0x41080  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInCrmInternalToolContext()
0x41085  brfalse.s loc_4108D
0x41087  call     string [mscorlib]System.Environment::get_CurrentDirectory()
0x4108c  ret
0x4108d  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x41092  brfalse.s loc_410AC
0x41094  ldstr    aCrmClientInsta// "CRM_Client_InstallDir"
0x41099  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x4109e  castclass [mscorlib]System.String
0x410a3  stloc.0
0x410a4  ldstr    aClientBinAssem// "client\\bin\\assembly\\"
0x410a9  stloc.1
0x410aa  br.s     loc_410C2
0x410ac  ldstr    aCrmServerInsta// "CRM_Server_InstallDir"
0x410b1  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x410b6  castclass [mscorlib]System.String
0x410bb  stloc.0
0x410bc  ldstr    aServerBinAssem// "server\\bin\\assembly\\"
0x410c1  stloc.1
0x410c2  ldloc.0
0x410c3  ldloc.1
0x410c4  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x410c9  ret
```
