# Microsoft.Crm.Application.ProcessControl.Configuration.BpfConfigurator::BuildSystemStepResourceStrings

- ea: `0x4ba10`
- end: `0x4bad1`
- name: `Microsoft.Crm.Application.ProcessControl.Configuration.BpfConfigurator::BuildSystemStepResourceStrings`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4b100`

## string_xrefs

- `0x4ba20`: `ProcessControl.Configurator.SystemSteps.IdentifyAccountDescription`
- `0x4ba40`: `ProcessControl.Configurator.SystemSteps.IdentifyContactDescription`
- `0x4ba60`: `ProcessControl.Configurator.SystemSteps.IdentifyCustomerDescription`
- `0x4ba80`: `ProcessControl.Configurator.SystemSteps.IdentifyIssueDescription`
- `0x4baa0`: `ProcessControl.Configurator.SystemSteps.Resolve`
- `0x4bac0`: `ProcessControl.Configurator.SystemSteps.Solutions`

## pseudocode

```c

```

## disassembly

```asm
0x4ba10  ldarg.0
0x4ba11  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4ba16  ldstr    aLocidSysstepId// "LOCID_SYSSTEP_IDACCOUNT"
0x4ba1b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4ba20  ldstr    aProcesscontrol_63// "ProcessControl.Configurator.SystemSteps"...
0x4ba25  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4ba2a  ldc.i4.0
0x4ba2b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4ba30  ldarg.0
0x4ba31  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4ba36  ldstr    aLocidSysstepId_0// "LOCID_SYSSTEP_IDCONTACT"
0x4ba3b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4ba40  ldstr    aProcesscontrol_64// "ProcessControl.Configurator.SystemSteps"...
0x4ba45  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4ba4a  ldc.i4.0
0x4ba4b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4ba50  ldarg.0
0x4ba51  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4ba56  ldstr    aLocidSysstepId_1// "LOCID_SYSSTEP_IDCUSTOMER"
0x4ba5b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4ba60  ldstr    aProcesscontrol_65// "ProcessControl.Configurator.SystemSteps"...
0x4ba65  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4ba6a  ldc.i4.0
0x4ba6b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4ba70  ldarg.0
0x4ba71  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4ba76  ldstr    aLocidSysstepId_2// "LOCID_SYSSTEP_IDISSUE"
0x4ba7b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4ba80  ldstr    aProcesscontrol_66// "ProcessControl.Configurator.SystemSteps"...
0x4ba85  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4ba8a  ldc.i4.0
0x4ba8b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4ba90  ldarg.0
0x4ba91  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4ba96  ldstr    aLocidSysstepRe// "LOCID_SYSSTEP_RESOLVE"
0x4ba9b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4baa0  ldstr    aProcesscontrol_67// "ProcessControl.Configurator.SystemSteps"...
0x4baa5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4baaa  ldc.i4.0
0x4baab  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4bab0  ldarg.0
0x4bab1  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x4bab6  ldstr    aLocidSysstepSo// "LOCID_SYSSTEP_SOLUTIONS"
0x4babb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4bac0  ldstr    aProcesscontrol_68// "ProcessControl.Configurator.SystemSteps"...
0x4bac5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4baca  ldc.i4.0
0x4bacb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x4bad0  ret
```
