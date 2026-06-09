# Microsoft.Crm.Controls.FilterPopup::ConstructPopupMenu

- ea: `0xc8c0`
- end: `0xc8dc`
- name: `Microsoft.Crm.Controls.FilterPopup::ConstructPopupMenu`
- size: `28`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd2b0`
- `0xd4e0`
- `0xd790`
- `0xe0e0`
- `0xe360`
- `0xe600`

## callees

- `0xce60`
- `0x118d0`

## string_xrefs

- `0xc8c6`: `xml_filter`

## pseudocode

```c

```

## disassembly

```asm
0xc8c0  ldarg.0
0xc8c1  call     instance class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Controls.CommandBarControl::get_CustomProperties()
0xc8c6  ldstr    aXmlFilter// "xml_filter"
0xc8cb  ldarg.0
0xc8cc  ldfld    class Microsoft.Crm.Controls.Selector Microsoft.Crm.Controls.FilterPopup::filterMenu
0xc8d1  callvirt instance string Microsoft.Crm.Controls.Selector::get_OuterXml()
0xc8d6  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0xc8db  ret
```
