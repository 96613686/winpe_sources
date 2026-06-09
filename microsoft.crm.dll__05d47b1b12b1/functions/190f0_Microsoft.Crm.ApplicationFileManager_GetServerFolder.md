# Microsoft.Crm.ApplicationFileManager::GetServerFolder

- ea: `0x190f0`
- end: `0x1912b`
- name: `Microsoft.Crm.ApplicationFileManager::GetServerFolder`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x190a0`

## callees

- `0x190f0`

## string_xrefs

- `0x190f7`: `CRM_Client_InstallDir`
- `0x19111`: `CRM_Server_InstallDir`

## pseudocode

```c

```

## disassembly

```asm
0x190f0  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x190f5  brfalse.s loc_19111
0x190f7  ldstr    aCrmClientInsta// "CRM_Client_InstallDir"
0x190fc  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x19101  castclass [mscorlib]System.String
0x19106  ldstr    aClient// "Client"
0x1910b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x19110  ret
0x19111  ldstr    aCrmServerInsta// "CRM_Server_InstallDir"
0x19116  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x1911b  castclass [mscorlib]System.String
0x19120  ldstr    aServer// "Server"
0x19125  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1912a  ret
```
