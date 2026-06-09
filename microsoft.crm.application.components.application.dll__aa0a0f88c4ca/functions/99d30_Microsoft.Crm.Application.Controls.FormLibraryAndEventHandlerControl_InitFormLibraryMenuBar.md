# Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::InitFormLibraryMenuBar

- ea: `0x99d30`
- end: `0x99f59`
- name: `Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::InitFormLibraryMenuBar`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x99910`

## callees

- `0x99d30`

## string_xrefs

- `0x99dc2`: `Form_Libraries_And_Event_Handler_Control_Remove`
- `0x99df6`: `Form_Libraries_And_Event_Handler_Control_Remove`
- `0x99de6`: `/_imgs/ico_16_remove.gif`
- `0x99e46`: `/_imgs/picklist/cmd_moveup.png`
- `0x99ea6`: `/_imgs/picklist/cmd_movedown.png`
- `0x99dcc`: `Mscrm.FormLibraryAndEventHandlerUtils.removeLibrary();`
- `0x99e00`: `removeLibrary`
- `0x99e2c`: `Mscrm.FormLibraryAndEventHandlerUtils.moveLibraryUp();`
- `0x99e60`: `moveLibraryUp`
- `0x99e8c`: `Mscrm.FormLibraryAndEventHandlerUtils.moveLibraryDown();`
- `0x99ec0`: `moveLibraryDown`

## pseudocode

```c

```

## disassembly

```asm
0x99d30  ldarg.0
0x99d31  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_formLibraryMenuBar
0x99d36  brtrue   loc_99F58
0x99d3b  ldarg.0
0x99d3c  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::.ctor()
0x99d41  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_formLibraryMenuBar
0x99d46  ldarg.0
0x99d47  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_formLibraryMenuBar
0x99d4c  ldstr    aLibrarymenubar// "libraryMenuBar"
0x99d51  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x99d56  ldarg.0
0x99d57  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_formLibraryMenuBar
0x99d5c  ldarg.0
0x99d5d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99d62  ldstr    aFormLibrariesA_0// "Form_Libraries_And_Event_Handler_Contro"...
0x99d67  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99d6c  ldstr    aMscrmFormlibra_5// "Mscrm.FormLibraryAndEventHandlerUtils.a"...
0x99d71  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x99d76  ldc.i4.1
0x99d77  newarr   [mscorlib]System.Char
0x99d7c  dup
0x99d7d  ldc.i4.0
0x99d7e  ldc.i4.s 0x2F
0x99d80  stelem.i2
0x99d81  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x99d86  ldstr    aImgsPicklistCm// "/_imgs/picklist/cmd_add.png"
0x99d8b  call     string [mscorlib]System.String::Concat(string, string)
0x99d90  ldarg.0
0x99d91  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99d96  ldstr    aFormLibrariesA_0// "Form_Libraries_And_Event_Handler_Contro"...
0x99d9b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99da0  ldstr    aAddlibrary// "addLibrary"
0x99da5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x99daa  pop
0x99dab  ldarg.0
0x99dac  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_formLibraryMenuBar
0x99db1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x99db6  ldarg.0
0x99db7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_formLibraryMenuBar
0x99dbc  ldarg.0
0x99dbd  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99dc2  ldstr    aFormLibrariesA_1// "Form_Libraries_And_Event_Handler_Contro"...
0x99dc7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99dcc  ldstr    aMscrmFormlibra_6// "Mscrm.FormLibraryAndEventHandlerUtils.r"...
0x99dd1  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x99dd6  ldc.i4.1
0x99dd7  newarr   [mscorlib]System.Char
0x99ddc  dup
0x99ddd  ldc.i4.0
0x99dde  ldc.i4.s 0x2F
0x99de0  stelem.i2
0x99de1  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x99de6  ldstr    aImgsIco16Remov_2// "/_imgs/ico_16_remove.gif"
0x99deb  call     string [mscorlib]System.String::Concat(string, string)
0x99df0  ldarg.0
0x99df1  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99df6  ldstr    aFormLibrariesA_1// "Form_Libraries_And_Event_Handler_Contro"...
0x99dfb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99e00  ldstr    aRemovelibrary// "removeLibrary"
0x99e05  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x99e0a  pop
0x99e0b  ldarg.0
0x99e0c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_formLibraryMenuBar
0x99e11  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x99e16  ldarg.0
0x99e17  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_formLibraryMenuBar
0x99e1c  ldarg.0
0x99e1d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99e22  ldstr    aFormLibrariesA_2// "Form_Libraries_And_Event_Handler_Contro"...
0x99e27  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99e2c  ldstr    aMscrmFormlibra_7// "Mscrm.FormLibraryAndEventHandlerUtils.m"...
0x99e31  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x99e36  ldc.i4.1
0x99e37  newarr   [mscorlib]System.Char
0x99e3c  dup
0x99e3d  ldc.i4.0
0x99e3e  ldc.i4.s 0x2F
0x99e40  stelem.i2
0x99e41  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x99e46  ldstr    aImgsPicklistCm_0// "/_imgs/picklist/cmd_moveup.png"
0x99e4b  call     string [mscorlib]System.String::Concat(string, string)
0x99e50  ldarg.0
0x99e51  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99e56  ldstr    aFormLibrariesA_2// "Form_Libraries_And_Event_Handler_Contro"...
0x99e5b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99e60  ldstr    aMovelibraryup// "moveLibraryUp"
0x99e65  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x99e6a  pop
0x99e6b  ldarg.0
0x99e6c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_formLibraryMenuBar
0x99e71  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x99e76  ldarg.0
0x99e77  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_formLibraryMenuBar
0x99e7c  ldarg.0
0x99e7d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99e82  ldstr    aFormLibrariesA_3// "Form_Libraries_And_Event_Handler_Contro"...
0x99e87  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99e8c  ldstr    aMscrmFormlibra_8// "Mscrm.FormLibraryAndEventHandlerUtils.m"...
0x99e91  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x99e96  ldc.i4.1
0x99e97  newarr   [mscorlib]System.Char
0x99e9c  dup
0x99e9d  ldc.i4.0
0x99e9e  ldc.i4.s 0x2F
0x99ea0  stelem.i2
0x99ea1  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x99ea6  ldstr    aImgsPicklistCm_1// "/_imgs/picklist/cmd_movedown.png"
0x99eab  call     string [mscorlib]System.String::Concat(string, string)
0x99eb0  ldarg.0
0x99eb1  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99eb6  ldstr    aFormLibrariesA_3// "Form_Libraries_And_Event_Handler_Contro"...
0x99ebb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99ec0  ldstr    aMovelibrarydow// "moveLibraryDown"
0x99ec5  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x99eca  pop
0x99ecb  ldarg.0
0x99ecc  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_formLibraryMenuBar
0x99ed1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x99ed6  ldarg.0
0x99ed7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_formLibraryMenuBar
0x99edc  ldarg.0
0x99edd  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99ee2  ldstr    aFormLibrariesA_6// "Form_Libraries_And_Event_Handler_Contro"...
0x99ee7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99eec  ldstr    aMscrmFormlibra_9// "Mscrm.FormLibraryAndEventHandlerUtils.e"...
0x99ef1  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x99ef6  ldc.i4.1
0x99ef7  newarr   [mscorlib]System.Char
0x99efc  dup
0x99efd  ldc.i4.0
0x99efe  ldc.i4.s 0x2F
0x99f00  stelem.i2
0x99f01  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x99f06  ldstr    aImgsFormeditor_0// "/_imgs/formeditorribbon/documentlibrary"...
0x99f0b  call     string [mscorlib]System.String::Concat(string, string)
0x99f10  ldarg.0
0x99f11  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99f16  ldstr    aFormLibrariesA_6// "Form_Libraries_And_Event_Handler_Contro"...
0x99f1b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99f20  ldstr    aEditlibrary// "editLibrary"
0x99f25  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x99f2a  pop
0x99f2b  ldarg.0
0x99f2c  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_formLibraryMenuBar
0x99f31  ldnull
0x99f32  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_ShadowCssClass(string)
0x99f37  ldarg.0
0x99f38  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_formLibraryMenuBar
0x99f3d  ldstr    aMsCrmActionbar// "ms-crm-ActionBar"
0x99f42  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_CssClass(string)
0x99f47  ldarg.0
0x99f48  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x99f4d  ldarg.0
0x99f4e  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_formLibraryMenuBar
0x99f53  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x99f58  ret
```
