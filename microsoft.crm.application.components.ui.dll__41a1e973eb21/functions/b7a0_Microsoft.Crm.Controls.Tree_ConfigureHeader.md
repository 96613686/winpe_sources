# Microsoft.Crm.Controls.Tree::ConfigureHeader

- ea: `0xb7a0`
- end: `0xb7f9`
- name: `Microsoft.Crm.Controls.Tree::ConfigureHeader`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2cf0`
- `0x2ef0`
- `0x3380`
- `0xb800`
- `0xb840`
- `0x23b60`
- `0x23d10`

## string_xrefs

- `0xb7ac`: `XML_LANGUAGE_NAME`

## pseudocode

```c

```

## disassembly

```asm
0xb7a0  ldarg.0
0xb7a1  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0xb7a6  ldarg.0
0xb7a7  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb7ac  ldstr    aXmlLanguageNam// "XML_LANGUAGE_NAME"
0xb7b1  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xb7b6  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_Parent()
0xb7bb  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xb7c0  callvirt instance string [mscorlib]System.Globalization.TextInfo::get_CultureName()
0xb7c5  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0xb7ca  ldarg.0
0xb7cb  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb7d0  ldstr    aStaticControls_19// "/_static/_controls/Tree/Tree.js"
0xb7d5  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0xb7da  ldarg.0
0xb7db  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0xb7e0  ldstr    aMscrmTree// "Mscrm.Tree"
0xb7e5  ldnull
0xb7e6  ldarg.0
0xb7e7  call     instance string Microsoft.Crm.Controls.Tree::get_ComponentEventsAsObjectLiteral()
0xb7ec  ldnull
0xb7ed  ldarg.0
0xb7ee  call     instance string Microsoft.Crm.Controls.Tree::get_TableCellId()
0xb7f3  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::CreateClientAjaxComponent(string componentTypeName, string properties, string events, string references, string elementId)
0xb7f8  ret
```
