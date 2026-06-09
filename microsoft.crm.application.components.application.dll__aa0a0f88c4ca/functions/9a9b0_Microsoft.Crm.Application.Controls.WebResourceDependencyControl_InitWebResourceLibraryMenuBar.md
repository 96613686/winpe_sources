# Microsoft.Crm.Application.Controls.WebResourceDependencyControl::InitWebResourceLibraryMenuBar

- ea: `0x9a9b0`
- end: `0x9aa6b`
- name: `Microsoft.Crm.Application.Controls.WebResourceDependencyControl::InitWebResourceLibraryMenuBar`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x9a9a0`

## callees

- `0x9a9b0`

## string_xrefs

- `0x9a9ed`: `Form_Libraries_And_Event_Handler_Control_Remove`
- `0x9aa2c`: `/_imgs/ico_16_remove.gif`
- `0x9aa32`: `removeLibrary`
- `0x9aa27`: `Mscrm.FormLibraryAndEventHandlerUtils.removeLibrary(true);`

## pseudocode

```c

```

## disassembly

```asm
0x9a9b0  ldarg.0
0x9a9b1  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_webResourceLibraryMenuBar
0x9a9b6  brtrue   loc_9AA6A
0x9a9bb  ldarg.0
0x9a9bc  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::.ctor()
0x9a9c1  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_webResourceLibraryMenuBar
0x9a9c6  ldarg.0
0x9a9c7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_webResourceLibraryMenuBar
0x9a9cc  ldstr    aLibrarymenubar// "libraryMenuBar"
0x9a9d1  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x9a9d6  ldarg.0
0x9a9d7  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_resourceManager
0x9a9dc  ldstr    aFormLibrariesA_0// "Form_Libraries_And_Event_Handler_Contro"...
0x9a9e1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a9e6  stloc.0
0x9a9e7  ldarg.0
0x9a9e8  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_resourceManager
0x9a9ed  ldstr    aFormLibrariesA_1// "Form_Libraries_And_Event_Handler_Contro"...
0x9a9f2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a9f7  stloc.1
0x9a9f8  ldarg.0
0x9a9f9  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_webResourceLibraryMenuBar
0x9a9fe  ldloc.0
0x9a9ff  ldstr    aMscrmFormlibra_14// "Mscrm.FormLibraryAndEventHandlerUtils.a"...
0x9aa04  ldstr    aImgsPicklistCm// "/_imgs/picklist/cmd_add.png"
0x9aa09  ldloc.0
0x9aa0a  ldstr    aAddlibrary// "addLibrary"
0x9aa0f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x9aa14  pop
0x9aa15  ldarg.0
0x9aa16  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_webResourceLibraryMenuBar
0x9aa1b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x9aa20  ldarg.0
0x9aa21  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_webResourceLibraryMenuBar
0x9aa26  ldloc.1
0x9aa27  ldstr    aMscrmFormlibra_15// "Mscrm.FormLibraryAndEventHandlerUtils.r"...
0x9aa2c  ldstr    aImgsIco16Remov_2// "/_imgs/ico_16_remove.gif"
0x9aa31  ldloc.1
0x9aa32  ldstr    aRemovelibrary// "removeLibrary"
0x9aa37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x9aa3c  pop
0x9aa3d  ldarg.0
0x9aa3e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_webResourceLibraryMenuBar
0x9aa43  ldnull
0x9aa44  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_ShadowCssClass(string)
0x9aa49  ldarg.0
0x9aa4a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_webResourceLibraryMenuBar
0x9aa4f  ldstr    aMsCrmActionbar// "ms-crm-ActionBar"
0x9aa54  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_CssClass(string)
0x9aa59  ldarg.0
0x9aa5a  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x9aa5f  ldarg.0
0x9aa60  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.WebResourceDependencyControl::_webResourceLibraryMenuBar
0x9aa65  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x9aa6a  ret
```
