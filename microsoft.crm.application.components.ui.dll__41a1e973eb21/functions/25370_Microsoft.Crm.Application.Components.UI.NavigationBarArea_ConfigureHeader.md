# Microsoft.Crm.Application.Components.UI.NavigationBarArea::ConfigureHeader

- ea: `0x25370`
- end: `0x253c6`
- name: `Microsoft.Crm.Application.Components.UI.NavigationBarArea::ConfigureHeader`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3380`
- `0x23b60`
- `0x23c20`
- `0x23d10`
- `0x23f10`
- `0x25240`
- `0x25260`
- `0x25370`

## string_xrefs

- `0x253a7`: `/_static/_common/styles/AutoToolTip.js`

## pseudocode

```c

```

## disassembly

```asm
0x25370  ldarg.0
0x25371  call     instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x25376  ldarg.0
0x25377  call     instance string Microsoft.Crm.Application.Components.UI.NavigationBarArea::get_RenderId()
0x2537c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x25381  brtrue.s loc_253C5
0x25383  ldarg.0
0x25384  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x25389  brtrue.s loc_253C5
0x2538b  ldarg.0
0x2538c  call     instance bool Microsoft.Crm.Application.Components.UI.NavigationBarArea::get_ShowHeader()
0x25391  brfalse.s loc_253C5
0x25393  ldarg.0
0x25394  ldfld    class [System]System.Collections.Generic.SortedDictionary`2<int32, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Components.UI.NavigationBarItem>> Microsoft.Crm.Application.Components.UI.NavigationBarArea::SortedControls
0x25399  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<int32, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Components.UI.NavigationBarItem>>::get_Count()
0x2539e  ldc.i4.0
0x2539f  ble.s    loc_253C5
0x253a1  ldarg.0
0x253a2  call     instance class Microsoft.Crm.Controls.PageResourceManager Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x253a7  ldstr    aStaticCommonSt// "/_static/_common/styles/AutoToolTip.js"
0x253ac  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string file)
0x253b1  ldarg.0
0x253b2  ldstr    aMscrmAutotoolt// "Mscrm.AutoToolTip"
0x253b7  ldnull
0x253b8  ldnull
0x253b9  ldnull
0x253ba  ldarg.0
0x253bb  call     instance string Microsoft.Crm.Application.Components.UI.NavigationBarArea::get_RenderId()
0x253c0  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string componentTypeName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> events, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> references, string elementId)
0x253c5  ret
```
