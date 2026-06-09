# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetWarningMessage

- ea: `0x4080`
- end: `0x411e`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetWarningMessage`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3620`
- `0x37a0`

## callees

- `0x4080`

## string_xrefs

- `0x40bc`: `ProcessControl.Warnings.InsufficientPrivilegesToViewProcess`

## pseudocode

```c

```

## disassembly

```asm
0x4080  ldarg.1
0x4081  ldc.i4.0
0x4082  stind.i4
0x4083  ldarg.0
0x4084  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessUserCacheEntry Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_processCacheEntry
0x4089  brtrue.s loc_408D
0x408b  ldnull
0x408c  ret
0x408d  ldarg.1
0x408e  ldarg.0
0x408f  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessUserCacheEntry Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_processCacheEntry
0x4094  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.AppProcessControlWarning [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessUserCacheEntry::get_Warning()
0x4099  stind.i4
0x409a  ldarg.1
0x409b  ldind.i4
0x409c  stloc.0
0x409d  ldloc.0
0x409e  switch   loc_40B5, loc_40B7, loc_40C7, loc_40FE
0x40b3  br.s     loc_410E
0x40b5  ldnull
0x40b6  ret
0x40b7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x40bc  ldstr    aProcesscontrol_39// "ProcessControl.Warnings.InsufficientPri"...
0x40c1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x40c6  ret
0x40c7  ldarg.0
0x40c8  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessUserCacheEntry Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::_processCacheEntry
0x40cd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.ProcessUserCacheEntry::get_ProcessId()
0x40d2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x40d7  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x40dc  brtrue.s loc_40EE
0x40de  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x40e3  ldstr    aProcesscontrol_40// "ProcessControl.Warnings.ProcessNotAvail"...
0x40e8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x40ed  ret
0x40ee  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x40f3  ldstr    aProcesscontrol_8// "ProcessControl.Warnings.ProcessWasChang"...
0x40f8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x40fd  ret
0x40fe  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4103  ldstr    aProcesscontrol_41// "ProcessControl.Warnings.ProcessIsNotAct"...
0x4108  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x410d  ret
0x410e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4113  ldstr    aProcesscontrol_42// "ProcessControl.Warnings.UnknownError"
0x4118  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x411d  ret
```
