# Microsoft.Crm.Sandbox.SandboxUtility::get_CrmServerInstallDirectory

- ea: `0x3440`
- end: `0x3462`
- name: `Microsoft.Crm.Sandbox.SandboxUtility::get_CrmServerInstallDirectory`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x82a0`

## callees

- `0x3440`

## string_xrefs

- `0x3447`: `CRM_Server_InstallDir`

## pseudocode

```c

```

## disassembly

```asm
0x3440  ldsfld   string Microsoft.Crm.Sandbox.SandboxUtility::_crmServerInstallDirectory
0x3445  brtrue.s loc_345C
0x3447  ldstr    aCrmServerInsta// "CRM_Server_InstallDir"
0x344c  ldnull
0x344d  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x3452  castclass [mscorlib]System.String
0x3457  stsfld   string Microsoft.Crm.Sandbox.SandboxUtility::_crmServerInstallDirectory
0x345c  ldsfld   string Microsoft.Crm.Sandbox.SandboxUtility::_crmServerInstallDirectory
0x3461  ret
```
