# Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::InitEventHandlerMenuBar

- ea: `0x99a90`
- end: `0x99d2c`
- name: `Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::InitEventHandlerMenuBar`
- size: `668`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x99920`

## callees

- `0x99a90`

## string_xrefs

- `0x99b35`: `Form_Libraries_And_Event_Handler_Control_Remove`
- `0x99b69`: `Form_Libraries_And_Event_Handler_Control_Remove`
- `0x99b3f`: `Mscrm.FormLibraryAndEventHandlerUtils.removeHandler();`
- `0x99b59`: `/_imgs/ico_16_remove.gif`
- `0x99b73`: `removeHandler`
- `0x99b9f`: `Mscrm.FormLibraryAndEventHandlerUtils.moveHandlerUp();`
- `0x99bb9`: `/_imgs/picklist/cmd_moveup.png`
- `0x99bd3`: `moveHandlerUp`
- `0x99bff`: `Mscrm.FormLibraryAndEventHandlerUtils.moveHandlerDown();`
- `0x99c19`: `/_imgs/picklist/cmd_movedown.png`
- `0x99c33`: `moveHandlerDown`

## pseudocode

```c

```

## disassembly

```asm
0x99a90  ldarg.0
0x99a91  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99a96  brtrue   loc_99D2B
0x99a9b  ldarg.0
0x99a9c  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::.ctor()
0x99aa1  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99aa6  ldarg.0
0x99aa7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99aac  ldstr    aEventhandlerme// "eventHandlerMenuBar"
0x99ab1  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x99ab6  ldarg.0
0x99ab7  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99abc  ldarg.0
0x99abd  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99ac2  ldstr    aFormLibrariesA_0// "Form_Libraries_And_Event_Handler_Contro"...
0x99ac7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99acc  ldstr    aMscrmFormlibra// "Mscrm.FormLibraryAndEventHandlerUtils.a"...
0x99ad1  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x99ad6  ldc.i4.1
0x99ad7  newarr   [mscorlib]System.Char
0x99adc  dup
0x99add  ldc.i4.0
0x99ade  ldc.i4.s 0x2F
0x99ae0  stelem.i2
0x99ae1  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x99ae6  ldstr    aImgsPicklistCm// "/_imgs/picklist/cmd_add.png"
0x99aeb  call     string [mscorlib]System.String::Concat(string, string)
0x99af0  ldarg.0
0x99af1  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99af6  ldstr    aFormLibrariesA_0// "Form_Libraries_And_Event_Handler_Contro"...
0x99afb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99b00  ldstr    aAddhandler// "addHandler"
0x99b05  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x99b0a  callvirt instance class [System.Web]System.Web.UI.AttributeCollection [System.Web]System.Web.UI.HtmlControls.HtmlControl::get_Attributes()
0x99b0f  ldstr    aSelectenable// "selectEnable"
0x99b14  ldstr    aTrue// "true"
0x99b19  callvirt instance void [System.Web]System.Web.UI.AttributeCollection::Add(string, string)
0x99b1e  ldarg.0
0x99b1f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99b24  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x99b29  ldarg.0
0x99b2a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99b2f  ldarg.0
0x99b30  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99b35  ldstr    aFormLibrariesA_1// "Form_Libraries_And_Event_Handler_Contro"...
0x99b3a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99b3f  ldstr    aMscrmFormlibra_0// "Mscrm.FormLibraryAndEventHandlerUtils.r"...
0x99b44  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x99b49  ldc.i4.1
0x99b4a  newarr   [mscorlib]System.Char
0x99b4f  dup
0x99b50  ldc.i4.0
0x99b51  ldc.i4.s 0x2F
0x99b53  stelem.i2
0x99b54  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x99b59  ldstr    aImgsIco16Remov_2// "/_imgs/ico_16_remove.gif"
0x99b5e  call     string [mscorlib]System.String::Concat(string, string)
0x99b63  ldarg.0
0x99b64  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99b69  ldstr    aFormLibrariesA_1// "Form_Libraries_And_Event_Handler_Contro"...
0x99b6e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99b73  ldstr    aRemovehandler// "removeHandler"
0x99b78  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x99b7d  pop
0x99b7e  ldarg.0
0x99b7f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99b84  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x99b89  ldarg.0
0x99b8a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99b8f  ldarg.0
0x99b90  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99b95  ldstr    aFormLibrariesA_2// "Form_Libraries_And_Event_Handler_Contro"...
0x99b9a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99b9f  ldstr    aMscrmFormlibra_1// "Mscrm.FormLibraryAndEventHandlerUtils.m"...
0x99ba4  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x99ba9  ldc.i4.1
0x99baa  newarr   [mscorlib]System.Char
0x99baf  dup
0x99bb0  ldc.i4.0
0x99bb1  ldc.i4.s 0x2F
0x99bb3  stelem.i2
0x99bb4  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x99bb9  ldstr    aImgsPicklistCm_0// "/_imgs/picklist/cmd_moveup.png"
0x99bbe  call     string [mscorlib]System.String::Concat(string, string)
0x99bc3  ldarg.0
0x99bc4  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99bc9  ldstr    aFormLibrariesA_2// "Form_Libraries_And_Event_Handler_Contro"...
0x99bce  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99bd3  ldstr    aMovehandlerup// "moveHandlerUp"
0x99bd8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x99bdd  pop
0x99bde  ldarg.0
0x99bdf  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99be4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x99be9  ldarg.0
0x99bea  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99bef  ldarg.0
0x99bf0  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99bf5  ldstr    aFormLibrariesA_3// "Form_Libraries_And_Event_Handler_Contro"...
0x99bfa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99bff  ldstr    aMscrmFormlibra_2// "Mscrm.FormLibraryAndEventHandlerUtils.m"...
0x99c04  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x99c09  ldc.i4.1
0x99c0a  newarr   [mscorlib]System.Char
0x99c0f  dup
0x99c10  ldc.i4.0
0x99c11  ldc.i4.s 0x2F
0x99c13  stelem.i2
0x99c14  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x99c19  ldstr    aImgsPicklistCm_1// "/_imgs/picklist/cmd_movedown.png"
0x99c1e  call     string [mscorlib]System.String::Concat(string, string)
0x99c23  ldarg.0
0x99c24  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99c29  ldstr    aFormLibrariesA_3// "Form_Libraries_And_Event_Handler_Contro"...
0x99c2e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99c33  ldstr    aMovehandlerdow// "moveHandlerDown"
0x99c38  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x99c3d  pop
0x99c3e  ldarg.0
0x99c3f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99c44  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x99c49  ldarg.0
0x99c4a  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99c4f  ldarg.0
0x99c50  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99c55  ldstr    aFormLibrariesA_4// "Form_Libraries_And_Event_Handler_Contro"...
0x99c5a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99c5f  ldstr    aMscrmFormlibra_3// "Mscrm.FormLibraryAndEventHandlerUtils.e"...
0x99c64  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x99c69  ldc.i4.1
0x99c6a  newarr   [mscorlib]System.Char
0x99c6f  dup
0x99c70  ldc.i4.0
0x99c71  ldc.i4.s 0x2F
0x99c73  stelem.i2
0x99c74  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x99c79  ldstr    aImgsFormeditor// "/_imgs/formeditorribbon/edithandler_16."...
0x99c7e  call     string [mscorlib]System.String::Concat(string, string)
0x99c83  ldarg.0
0x99c84  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99c89  ldstr    aFormLibrariesA_4// "Form_Libraries_And_Event_Handler_Contro"...
0x99c8e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99c93  ldstr    aEdithandler// "editHandler"
0x99c98  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x99c9d  pop
0x99c9e  ldarg.0
0x99c9f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99ca4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x99ca9  ldarg.0
0x99caa  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99caf  ldarg.0
0x99cb0  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99cb5  ldstr    aFormLibrariesA_5// "Form_Libraries_And_Event_Handler_Contro"...
0x99cba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99cbf  ldstr    aMscrmFormlibra_4// "Mscrm.FormLibraryAndEventHandlerUtils.e"...
0x99cc4  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x99cc9  ldc.i4.1
0x99cca  newarr   [mscorlib]System.Char
0x99ccf  dup
0x99cd0  ldc.i4.0
0x99cd1  ldc.i4.s 0x2F
0x99cd3  stelem.i2
0x99cd4  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x99cd9  ldstr    aImgsFormeditor_0// "/_imgs/formeditorribbon/documentlibrary"...
0x99cde  call     string [mscorlib]System.String::Concat(string, string)
0x99ce3  ldarg.0
0x99ce4  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x99ce9  ldstr    aFormLibrariesA_5// "Form_Libraries_And_Event_Handler_Contro"...
0x99cee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x99cf3  ldstr    aEdithandlerlib// "editHandlerLibrary"
0x99cf8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x99cfd  pop
0x99cfe  ldarg.0
0x99cff  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99d04  ldnull
0x99d05  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_ShadowCssClass(string)
0x99d0a  ldarg.0
0x99d0b  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99d10  ldstr    aMsCrmActionbar// "ms-crm-ActionBar"
0x99d15  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_CssClass(string)
0x99d1a  ldarg.0
0x99d1b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x99d20  ldarg.0
0x99d21  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_eventHandlerMenuBar
0x99d26  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x99d2b  ret
```
