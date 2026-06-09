# Microsoft.Crm.Tools.Admin.DMSnapInLibCache::get_ApplicationPath

- ea: `0x44b0`
- end: `0x44c0`
- name: `Microsoft.Crm.Tools.Admin.DMSnapInLibCache::get_ApplicationPath`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x19020`

## string_xrefs

- `0x44b0`: `CRM_Server_InstallDir`

## pseudocode

```c

```

## disassembly

```asm
0x44b0  ldstr    aCrmServerInsta// "CRM_Server_InstallDir"
0x44b5  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x44ba  castclass [mscorlib]System.String
0x44bf  ret
```
