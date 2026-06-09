# Microsoft.Crm.Service.SM.ResourceSpecifications.CreateGroupPage::ConfigurePage

- ea: `0x1240`
- end: `0x1278`
- name: `Microsoft.Crm.Service.SM.ResourceSpecifications.CreateGroupPage::ConfigurePage`
- size: `56`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x1267`: `Create_Resource_Group_Dialog_No_Name`

## pseudocode

```c

```

## disassembly

```asm
0x1240  ldarg.0
0x1241  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x1246  ldarg.0
0x1247  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x124c  ldstr    aSmResourcespec// "/sm/resourcespecs/resourceruledialog.cs"...
0x1251  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x1256  ldarg.0
0x1257  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x125c  ldstr    aLocidNoGroupNa// "LOCID_NO_GROUP_NAME"
0x1261  ldarg.0
0x1262  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1267  ldstr    aCreateResource// "Create_Resource_Group_Dialog_No_Name"
0x126c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1271  ldc.i4.0
0x1272  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1277  ret
```
