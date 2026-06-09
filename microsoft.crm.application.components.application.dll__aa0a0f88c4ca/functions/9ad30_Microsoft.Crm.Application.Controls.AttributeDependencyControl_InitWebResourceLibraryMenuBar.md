# Microsoft.Crm.Application.Controls.AttributeDependencyControl::InitWebResourceLibraryMenuBar

- ea: `0x9ad30`
- end: `0x9adf6`
- name: `Microsoft.Crm.Application.Controls.AttributeDependencyControl::InitWebResourceLibraryMenuBar`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x9ad20`

## callees

- `0x9ad30`

## string_xrefs

- `0x9ad6d`: `Form_Libraries_And_Event_Handler_Control_Remove`
- `0x9adac`: `/_imgs/ico_16_remove.gif`
- `0x9ada7`: `Mscrm.FormLibraryAndEventHandlerUtils.removeAttribute(true);`
- `0x9adb2`: `removeAttribute`

## pseudocode

```c

```

## disassembly

```asm
0x9ad30  ldarg.0
0x9ad31  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AttributeDependencyControl::_webResourceLibraryMenuBar
0x9ad36  brtrue   loc_9ADF5
0x9ad3b  ldarg.0
0x9ad3c  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::.ctor()
0x9ad41  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AttributeDependencyControl::_webResourceLibraryMenuBar
0x9ad46  ldarg.0
0x9ad47  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AttributeDependencyControl::_webResourceLibraryMenuBar
0x9ad4c  ldstr    aAttributemenub// "attributeMenuBar"
0x9ad51  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x9ad56  ldarg.0
0x9ad57  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AttributeDependencyControl::_resourceManager
0x9ad5c  ldstr    aFormLibrariesA_0// "Form_Libraries_And_Event_Handler_Contro"...
0x9ad61  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ad66  stloc.0
0x9ad67  ldarg.0
0x9ad68  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.AttributeDependencyControl::_resourceManager
0x9ad6d  ldstr    aFormLibrariesA_1// "Form_Libraries_And_Event_Handler_Contro"...
0x9ad72  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9ad77  stloc.1
0x9ad78  ldarg.0
0x9ad79  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AttributeDependencyControl::_webResourceLibraryMenuBar
0x9ad7e  ldloc.0
0x9ad7f  ldstr    aMscrmFormlibra_16// "Mscrm.FormLibraryAndEventHandlerUtils.a"...
0x9ad84  ldstr    aImgsPicklistCm// "/_imgs/picklist/cmd_add.png"
0x9ad89  ldloc.0
0x9ad8a  ldstr    aAddattribute// "addAttribute"
0x9ad8f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x9ad94  pop
0x9ad95  ldarg.0
0x9ad96  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AttributeDependencyControl::_webResourceLibraryMenuBar
0x9ad9b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x9ada0  ldarg.0
0x9ada1  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AttributeDependencyControl::_webResourceLibraryMenuBar
0x9ada6  ldloc.1
0x9ada7  ldstr    aMscrmFormlibra_17// "Mscrm.FormLibraryAndEventHandlerUtils.r"...
0x9adac  ldstr    aImgsIco16Remov_2// "/_imgs/ico_16_remove.gif"
0x9adb1  ldloc.1
0x9adb2  ldstr    aRemoveattribut// "removeAttribute"
0x9adb7  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x9adbc  pop
0x9adbd  ldarg.0
0x9adbe  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AttributeDependencyControl::_webResourceLibraryMenuBar
0x9adc3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x9adc8  ldarg.0
0x9adc9  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AttributeDependencyControl::_webResourceLibraryMenuBar
0x9adce  ldnull
0x9adcf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_ShadowCssClass(string)
0x9add4  ldarg.0
0x9add5  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AttributeDependencyControl::_webResourceLibraryMenuBar
0x9adda  ldstr    aMsCrmActionbar// "ms-crm-ActionBar"
0x9addf  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_CssClass(string)
0x9ade4  ldarg.0
0x9ade5  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x9adea  ldarg.0
0x9adeb  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.AttributeDependencyControl::_webResourceLibraryMenuBar
0x9adf0  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x9adf5  ret
```
