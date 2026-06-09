# Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_AllCompany

- ea: `0x7750`
- end: `0x7760`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_AllCompany`
- size: `16`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7950`
- `0x79f0`

## string_xrefs

- `0x7755`: `Web.Tools.Yammer.Config.AllCompany`

## pseudocode

```c

```

## disassembly

```asm
0x7750  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x7755  ldstr    aWebToolsYammer// "Web.Tools.Yammer.Config.AllCompany"
0x775a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x775f  ret
```
