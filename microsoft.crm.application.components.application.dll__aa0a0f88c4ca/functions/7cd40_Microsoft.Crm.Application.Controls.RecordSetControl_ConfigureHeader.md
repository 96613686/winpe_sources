# Microsoft.Crm.Application.Controls.RecordSetControl::ConfigureHeader

- ea: `0x7cd40`
- end: `0x7ce9a`
- name: `Microsoft.Crm.Application.Controls.RecordSetControl::ConfigureHeader`
- size: `346`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x7ccc0`
- `0x7cce0`
- `0x7cd00`
- `0x7cd40`

## string_xrefs

- `0x7ce15`: `MenuItem_Label_Copy_Shortcut`
- `0x7cdd4`: `openActionTitle`
- `0x7cddf`: `Grid_RenderContextMenu_Label_Open`
- `0x7cdef`: `openInNewWindowActionTitle`
- `0x7cdfa`: `Grid_RenderContextMenu_Label_OpenInNewWindow`
- `0x7ce0a`: `copyShortcutActionTitle`
- `0x7ce79`: `/_static/_common/scripts/maincontrols.js`

## pseudocode

```c

```

## disassembly

```asm
0x7cd40  ldarg.0
0x7cd41  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::ConfigureHeader()
0x7cd46  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x7cd4b  stloc.0
0x7cd4c  ldloc.0
0x7cd4d  ldstr    aPagingmask// "pagingMask"
0x7cd52  ldarg.0
0x7cd53  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.RecordSetControl::get_CurrentResourceManager()
0x7cd58  ldstr    aGridPagingMask// "Grid_Paging_Mask"
0x7cd5d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7cd62  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x7cd67  ldloc.0
0x7cd68  ldstr    aViewprefix// "viewPrefix"
0x7cd6d  ldarg.0
0x7cd6e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.RecordSetControl::get_CurrentResourceManager()
0x7cd73  ldstr    aFormRecordsele// "Form_RecordSelector_ViewPrefix"
0x7cd78  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7cd7d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x7cd82  ldloc.0
0x7cd83  ldstr    aFirstpagetoolt// "firstPageToolTip"
0x7cd88  ldarg.0
0x7cd89  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.RecordSetControl::get_CurrentResourceManager()
0x7cd8e  ldstr    aGridTooltipFir// "Grid_ToolTip_FirstPage"
0x7cd93  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7cd98  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x7cd9d  ldloc.0
0x7cd9e  ldstr    aPreviouspageto// "previousPageToolTip"
0x7cda3  ldarg.0
0x7cda4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.RecordSetControl::get_CurrentResourceManager()
0x7cda9  ldstr    aGridTooltipPre// "Grid_ToolTip_PreviousPage"
0x7cdae  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7cdb3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x7cdb8  ldloc.0
0x7cdb9  ldstr    aNextpagetoolti// "nextPageToolTip"
0x7cdbe  ldarg.0
0x7cdbf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.RecordSetControl::get_CurrentResourceManager()
0x7cdc4  ldstr    aGridTooltipNex// "Grid_ToolTip_NextPage"
0x7cdc9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7cdce  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x7cdd3  ldloc.0
0x7cdd4  ldstr    aOpenactiontitl// "openActionTitle"
0x7cdd9  ldarg.0
0x7cdda  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.RecordSetControl::get_CurrentResourceManager()
0x7cddf  ldstr    aGridRendercont// "Grid_RenderContextMenu_Label_Open"
0x7cde4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7cde9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x7cdee  ldloc.0
0x7cdef  ldstr    aOpeninnewwindo// "openInNewWindowActionTitle"
0x7cdf4  ldarg.0
0x7cdf5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.RecordSetControl::get_CurrentResourceManager()
0x7cdfa  ldstr    aGridRendercont_0// "Grid_RenderContextMenu_Label_OpenInNewW"...
0x7cdff  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7ce04  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x7ce09  ldloc.0
0x7ce0a  ldstr    aCopyshortcutac// "copyShortcutActionTitle"
0x7ce0f  ldarg.0
0x7ce10  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.RecordSetControl::get_CurrentResourceManager()
0x7ce15  ldstr    aMenuitemLabelC_0// "MenuItem_Label_Copy_Shortcut"
0x7ce1a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7ce1f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x7ce24  ldloc.0
0x7ce25  ldstr    aSendshortcutac// "sendShortcutActionTitle"
0x7ce2a  ldarg.0
0x7ce2b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.RecordSetControl::get_CurrentResourceManager()
0x7ce30  ldstr    aMenuitemLabelS_5// "MenuItem_Label_Send_Shortcut"
0x7ce35  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7ce3a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x7ce3f  ldloc.0
0x7ce40  ldstr    aShowrecordsetm// "showRecordSetMenu"
0x7ce45  ldarg.0
0x7ce46  call     instance bool Microsoft.Crm.Application.Controls.RecordSetControl::get_ShowRecordSetMenu()
0x7ce4b  box      [mscorlib]System.Boolean
0x7ce50  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x7ce55  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x7ce5a  stloc.1
0x7ce5b  ldarg.0
0x7ce5c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.EventManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_EventManager()
0x7ce61  brtrue.s loc_7CE73
0x7ce63  ldloc.1
0x7ce64  ldstr    aEventmanager// "eventManager"
0x7ce69  ldstr    aPageCrmeventma// "__Page_crmEventManager"
0x7ce6e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x7ce73  ldarg.0
0x7ce74  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7ce79  ldstr    aStaticCommonSc_11// "/_static/_common/scripts/maincontrols.j"...
0x7ce7e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x7ce83  ldarg.0
0x7ce84  ldarg.0
0x7ce85  call     instance string Microsoft.Crm.Application.Controls.RecordSetControl::get_ClientControlName()
0x7ce8a  ldloc.0
0x7ce8b  ldnull
0x7ce8c  ldloc.1
0x7ce8d  ldarg.0
0x7ce8e  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x7ce93  ldc.i4.1
0x7ce94  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string, bool)
0x7ce99  ret
```
