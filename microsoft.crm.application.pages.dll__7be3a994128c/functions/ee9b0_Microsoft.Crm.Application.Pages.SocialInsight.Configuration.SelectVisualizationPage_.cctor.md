# Microsoft.Crm.Application.Pages.SocialInsight.Configuration.SelectVisualizationPage::.cctor

- ea: `0xee9b0`
- end: `0xeea9b`
- name: `Microsoft.Crm.Application.Pages.SocialInsight.Configuration.SelectVisualizationPage::.cctor`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, registry_config, broker_com_uri`

## string_xrefs

- `0xee9bb`: `NetBreeze.WidgetList.Buttons.MoveUp`
- `0xee9cb`: `NetBreeze.WidgetList.Buttons.MoveDown`
- `0xee9eb`: `NetBreeze.WidgetList.Buttons.Delete`
- `0xeea66`: `LOCID_PROCESS_MOVE`
- `0xeea6b`: `Common.ListEditing.MoveCaptialized`
- `0xeea76`: `LOCID_PROCESS_MOVE_DOWN`
- `0xeea7b`: `Common.ListEditing.MoveDownCaptialized`
- `0xeea86`: `LOCID_PROCESS_MOVE_UP`
- `0xeea8b`: `Common.ListEditing.MoveUpCaptialized`

## pseudocode

```c

```

## disassembly

```asm
0xee9b0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0xee9b5  dup
0xee9b6  ldstr    aLocidNetbreeze_11// "LOCID_NETBREEZE_WIDGET_UP"
0xee9bb  ldstr    aNetbreezeWidge// "NetBreeze.WidgetList.Buttons.MoveUp"
0xee9c0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xee9c5  dup
0xee9c6  ldstr    aLocidNetbreeze_12// "LOCID_NETBREEZE_WIDGET_DOWN"
0xee9cb  ldstr    aNetbreezeWidge_0// "NetBreeze.WidgetList.Buttons.MoveDown"
0xee9d0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xee9d5  dup
0xee9d6  ldstr    aLocidNetbreeze_13// "LOCID_NETBREEZE_WIDGET_ADD"
0xee9db  ldstr    aNetbreezeWidge_1// "NetBreeze.WidgetList.Buttons.Add"
0xee9e0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xee9e5  dup
0xee9e6  ldstr    aLocidNetbreeze_14// "LOCID_NETBREEZE_WIDGET_DEL"
0xee9eb  ldstr    aNetbreezeWidge_2// "NetBreeze.WidgetList.Buttons.Delete"
0xee9f0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xee9f5  dup
0xee9f6  ldstr    aLocidNetbreeze_15// "LOCID_NETBREEZE_HEAD_TYPE"
0xee9fb  ldstr    aNetbreezeWidge_3// "NetBreeze.WidgetList.Header.Type"
0xeea00  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xeea05  dup
0xeea06  ldstr    aLocidNetbreeze_16// "LOCID_NETBREEZE_HEAD_DESCR"
0xeea0b  ldstr    aNetbreezeWidge_4// "NetBreeze.WidgetList.Header.Description"
0xeea10  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xeea15  dup
0xeea16  ldstr    aLocidNetbreeze_17// "LOCID_NETBREEZE_HEAD_PREVIEW"
0xeea1b  ldstr    aNetbreezeWidge_5// "NetBreeze.WidgetList.Header.Preview"
0xeea20  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xeea25  dup
0xeea26  ldstr    aLocidNetbreeze_18// "LOCID_NETBREEZE_SHOW_FILTERS"
0xeea2b  ldstr    aNetbreezeWidge_6// "NetBreeze.WidgetList.ShowFilters"
0xeea30  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xeea35  dup
0xeea36  ldstr    aLocidNetbreeze_19// "LOCID_NETBREEZE_ITEM_CAPTION"
0xeea3b  ldstr    aNetbreezeWidge_7// "NetBreeze.WidgetList.SearchItemCaption"
0xeea40  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xeea45  dup
0xeea46  ldstr    aLocidNetbreeze_20// "LOCID_NETBREEZE_CATEGORY_CAPTION"
0xeea4b  ldstr    aNetbreezeWidge_8// "NetBreeze.WidgetList.SearchCategoryCapt"...
0xeea50  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xeea55  dup
0xeea56  ldstr    aLocidNetbreeze_21// "LOCID_NETBREEZE_ERR_UNSUPPORTED"
0xeea5b  ldstr    aNetbreezeWidge_9// "NetBreeze.WidgetList.Errors.Unsupported"...
0xeea60  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xeea65  dup
0xeea66  ldstr    aLocidProcessMo// "LOCID_PROCESS_MOVE"
0xeea6b  ldstr    aCommonListedit// "Common.ListEditing.MoveCaptialized"
0xeea70  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xeea75  dup
0xeea76  ldstr    aLocidProcessMo_0// "LOCID_PROCESS_MOVE_DOWN"
0xeea7b  ldstr    aCommonListedit_0// "Common.ListEditing.MoveDownCaptialized"
0xeea80  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xeea85  dup
0xeea86  ldstr    aLocidProcessMo_1// "LOCID_PROCESS_MOVE_UP"
0xeea8b  ldstr    aCommonListedit_1// "Common.ListEditing.MoveUpCaptialized"
0xeea90  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0xeea95  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Pages.SocialInsight.Configuration.SelectVisualizationPage::localizedStrings
0xeea9a  ret
```
