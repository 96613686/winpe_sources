# Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildAsyncOperationMenuBar

- ea: `0x21ef0`
- end: `0x21f8b`
- name: `Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildAsyncOperationMenuBar`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1b610`

## callees

- `0x1b380`
- `0x1c010`
- `0x24210`

## string_xrefs

- `0x21f21`: `Menu_Label_Completed_AsyncOperation`
- `0x21f3d`: `Menu_Label_Ready_AsyncOperation`
- `0x21eff`: `LOCID_POSTPONE_COMPLETED_JOB`
- `0x21f0a`: `Error_Message.WorkflowJob.State.Completed`

## pseudocode

```c

```

## disassembly

```asm
0x21ef0  ldarg.0
0x21ef1  ldc.i4.2
0x21ef2  ldc.i4.0
0x21ef3  ldc.i4.1
0x21ef4  call     instance void Microsoft.Crm.Application.Menus.AppGridMenuBar::BuildStandardActionsMenu(valuetype Microsoft.Crm.Application.Menus.GridActionParameters actionParam, bool buttonNew, bool buttonExport)
0x21ef9  ldarg.0
0x21efa  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x21eff  ldstr    aLocidPostponeC// "LOCID_POSTPONE_COMPLETED_JOB"
0x21f04  ldarg.0
0x21f05  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x21f0a  ldstr    aErrorMessageWo// "Error_Message.WorkflowJob.State.Complet"...
0x21f0f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21f14  ldc.i4.0
0x21f15  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x21f1a  ldarg.0
0x21f1b  ldarg.0
0x21f1c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x21f21  ldstr    aMenuLabelCompl// "Menu_Label_Completed_AsyncOperation"
0x21f26  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21f2b  ldstr    aAsyncoperation// "asyncOperationCancel"
0x21f30  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x21f35  pop
0x21f36  ldarg.0
0x21f37  ldarg.0
0x21f38  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x21f3d  ldstr    aMenuLabelReady// "Menu_Label_Ready_AsyncOperation"
0x21f42  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21f47  ldstr    aAsyncoperation_0// "asyncOperationResume"
0x21f4c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x21f51  pop
0x21f52  ldarg.0
0x21f53  ldarg.0
0x21f54  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x21f59  ldstr    aMenuLabelSuspe// "Menu_Label_Suspended_AsyncOperation"
0x21f5e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21f63  ldstr    aAsyncoperation_1// "asyncOperationPostpone"
0x21f68  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x21f6d  pop
0x21f6e  ldarg.0
0x21f6f  ldarg.0
0x21f70  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x21f75  ldstr    aMenuLabelPause// "Menu_Label_Paused_AsyncOperation"
0x21f7a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21f7f  ldstr    aAsyncoperation_2// "asyncOperationPause"
0x21f84  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl Microsoft.Crm.Application.Menus.AppGridMenuBar::AddMenuItemDoAction(string name, string action)
0x21f89  pop
0x21f8a  ret
```
