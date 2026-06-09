# Microsoft.Crm.Application.Controls.AnonymousHelpPage::ConfigureHeader

- ea: `0x8e830`
- end: `0x8e8a5`
- name: `Microsoft.Crm.Application.Controls.AnonymousHelpPage::ConfigureHeader`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8e1f0`
- `0x8e350`

## string_xrefs

- `0x8e87a`: `/help/common/fonts.css.aspx`
- `0x8e88a`: `/help/common/global.css.aspx`
- `0x8e89a`: `/help/common/menu.css.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x8e830  ldarg.0
0x8e831  call     instance class Microsoft.Crm.Application.Controls.AnonymousHeader Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0x8e836  ldc.i4.1
0x8e837  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_HelpContext(bool)
0x8e83c  ldarg.0
0x8e83d  call     instance class Microsoft.Crm.Application.Controls.AnonymousHeader Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0x8e842  ldstr    aUserHelpLcid// "USER_HELP_LCID"
0x8e847  ldarg.0
0x8e848  call     instance int32 Microsoft.Crm.Application.Controls.AnonymousHelpPage::get_HelpLcid()
0x8e84d  stloc.0
0x8e84e  ldloca.s 0
0x8e850  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8e855  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x8e85a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8e85f  ldarg.0
0x8e860  call     instance class Microsoft.Crm.Application.Controls.AnonymousHeader Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0x8e865  ldstr    aHelpContext// "HELP_CONTEXT"
0x8e86a  ldstr    a1_0// "1"
0x8e86f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x8e874  ldarg.0
0x8e875  call     instance class Microsoft.Crm.Application.Controls.AnonymousHeader Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0x8e87a  ldstr    aHelpCommonFont// "/help/common/fonts.css.aspx"
0x8e87f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8e884  ldarg.0
0x8e885  call     instance class Microsoft.Crm.Application.Controls.AnonymousHeader Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0x8e88a  ldstr    aHelpCommonGlob// "/help/common/global.css.aspx"
0x8e88f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8e894  ldarg.0
0x8e895  call     instance class Microsoft.Crm.Application.Controls.AnonymousHeader Microsoft.Crm.Application.Controls.AnonymousPage::get_CurrentHeader()
0x8e89a  ldstr    aHelpCommonMenu// "/help/common/menu.css.aspx"
0x8e89f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x8e8a4  ret
```
