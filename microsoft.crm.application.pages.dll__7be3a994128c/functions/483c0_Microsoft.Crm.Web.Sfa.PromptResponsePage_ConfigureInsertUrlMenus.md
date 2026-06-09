# Microsoft.Crm.Web.Sfa.PromptResponsePage::ConfigureInsertUrlMenus

- ea: `0x483c0`
- end: `0x484ab`
- name: `Microsoft.Crm.Web.Sfa.PromptResponsePage::ConfigureInsertUrlMenus`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x48370`

## callees

- `0x483c0`

## string_xrefs

- `0x483e3`: `prHyperlinkBar`
- `0x483f8`: `prHyperlinkBar`
- `0x4841c`: `addHyperlinkPrompt();`
- `0x48436`: `/_imgs/inserthyperlink_16.png`
- `0x48485`: `/_imgs/inserthyperlink_16.png`
- `0x48446`: `Web.SFA.InteractiveWorkflow.AddHyperlink`
- `0x48495`: `Web.SFA.InteractiveWorkflow.AddHyperlink`
- `0x48450`: `hyperlinkPrompt`
- `0x4846b`: `addHyperlinkCue();`
- `0x4849f`: `hyperlinkCue`

## pseudocode

```c

```

## disassembly

```asm
0x483c0  ldarg.0
0x483c1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Web.Sfa.PromptResponsePage::promptTextMenuBar
0x483c6  ldc.i4.0
0x483c7  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::Execute(bool)
0x483cc  ldarg.0
0x483cd  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Web.Sfa.PromptResponsePage::cueTextMenuBar
0x483d2  ldc.i4.0
0x483d3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::Execute(bool)
0x483d8  ldarg.0
0x483d9  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Web.Sfa.PromptResponsePage::promptTextMenuBar
0x483de  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x483e3  ldstr    aPrhyperlinkbar// "prHyperlinkBar"
0x483e8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_CssClass(string)
0x483ed  ldarg.0
0x483ee  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Web.Sfa.PromptResponsePage::cueTextMenuBar
0x483f3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x483f8  ldstr    aPrhyperlinkbar// "prHyperlinkBar"
0x483fd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::set_CssClass(string)
0x48402  ldsfld   bool Microsoft.Crm.Web.Sfa.PromptResponsePage::isReadOnlyMode
0x48407  brtrue   loc_484AA
0x4840c  ldarg.0
0x4840d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Web.Sfa.PromptResponsePage::promptTextMenuBar
0x48412  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x48417  ldsfld   string [mscorlib]System.String::Empty
0x4841c  ldstr    aAddhyperlinkpr// "addHyperlinkPrompt();"
0x48421  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x48426  ldc.i4.1
0x48427  newarr   [mscorlib]System.Char
0x4842c  dup
0x4842d  ldc.i4.0
0x4842e  ldc.i4.s 0x2F
0x48430  stelem.i2
0x48431  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x48436  ldstr    aImgsInserthype// "/_imgs/inserthyperlink_16.png"
0x4843b  call     string [mscorlib]System.String::Concat(string, string)
0x48440  ldarg.0
0x48441  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x48446  ldstr    aWebSfaInteract_17// "Web.SFA.InteractiveWorkflow.AddHyperlin"...
0x4844b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x48450  ldstr    aHyperlinkpromp// "hyperlinkPrompt"
0x48455  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x4845a  pop
0x4845b  ldarg.0
0x4845c  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppGridMenuBar Microsoft.Crm.Web.Sfa.PromptResponsePage::cueTextMenuBar
0x48461  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.AppMenuBar::get_MenuBar()
0x48466  ldsfld   string [mscorlib]System.String::Empty
0x4846b  ldstr    aAddhyperlinkcu// "addHyperlinkCue();"
0x48470  call     string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x48475  ldc.i4.1
0x48476  newarr   [mscorlib]System.Char
0x4847b  dup
0x4847c  ldc.i4.0
0x4847d  ldc.i4.s 0x2F
0x4847f  stelem.i2
0x48480  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x48485  ldstr    aImgsInserthype// "/_imgs/inserthyperlink_16.png"
0x4848a  call     string [mscorlib]System.String::Concat(string, string)
0x4848f  ldarg.0
0x48490  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x48495  ldstr    aWebSfaInteract_17// "Web.SFA.InteractiveWorkflow.AddHyperlin"...
0x4849a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4849f  ldstr    aHyperlinkcue// "hyperlinkCue"
0x484a4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarButton [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddButton(string, string, string, string, string)
0x484a9  pop
0x484aa  ret
```
