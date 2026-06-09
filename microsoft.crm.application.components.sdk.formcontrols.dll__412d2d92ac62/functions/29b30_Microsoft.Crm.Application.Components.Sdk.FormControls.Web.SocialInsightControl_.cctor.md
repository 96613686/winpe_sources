# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::.cctor

- ea: `0x29b30`
- end: `0x29c1b`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::.cctor`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## string_xrefs

- `0x29b3b`: `NetBreeze.WidgetList.Buttons.MoveUp`
- `0x29b4b`: `NetBreeze.WidgetList.Buttons.MoveDown`
- `0x29b6b`: `NetBreeze.WidgetList.Buttons.Delete`
- `0x29be6`: `LOCID_PROCESS_MOVE`
- `0x29beb`: `Common.ListEditing.MoveCaptialized`
- `0x29bf6`: `LOCID_PROCESS_MOVE_DOWN`
- `0x29bfb`: `Common.ListEditing.MoveDownCaptialized`
- `0x29c06`: `LOCID_PROCESS_MOVE_UP`
- `0x29c0b`: `Common.ListEditing.MoveUpCaptialized`

## pseudocode

```c

```

## disassembly

```asm
0x29b30  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x29b35  dup
0x29b36  ldstr    aLocidNetbreeze// "LOCID_NETBREEZE_WIDGET_UP"
0x29b3b  ldstr    aNetbreezeWidge// "NetBreeze.WidgetList.Buttons.MoveUp"
0x29b40  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x29b45  dup
0x29b46  ldstr    aLocidNetbreeze_0// "LOCID_NETBREEZE_WIDGET_DOWN"
0x29b4b  ldstr    aNetbreezeWidge_0// "NetBreeze.WidgetList.Buttons.MoveDown"
0x29b50  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x29b55  dup
0x29b56  ldstr    aLocidNetbreeze_1// "LOCID_NETBREEZE_WIDGET_ADD"
0x29b5b  ldstr    aNetbreezeWidge_1// "NetBreeze.WidgetList.Buttons.Add"
0x29b60  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x29b65  dup
0x29b66  ldstr    aLocidNetbreeze_2// "LOCID_NETBREEZE_WIDGET_DEL"
0x29b6b  ldstr    aNetbreezeWidge_2// "NetBreeze.WidgetList.Buttons.Delete"
0x29b70  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x29b75  dup
0x29b76  ldstr    aLocidNetbreeze_3// "LOCID_NETBREEZE_HEAD_INDEX"
0x29b7b  ldstr    aNetbreezeWidge_3// "NetBreeze.WidgetList.Header.Index"
0x29b80  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x29b85  dup
0x29b86  ldstr    aLocidNetbreeze_4// "LOCID_NETBREEZE_HEAD_TYPE"
0x29b8b  ldstr    aNetbreezeWidge_4// "NetBreeze.WidgetList.Header.Type"
0x29b90  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x29b95  dup
0x29b96  ldstr    aLocidNetbreeze_5// "LOCID_NETBREEZE_HEAD_DESCR"
0x29b9b  ldstr    aNetbreezeWidge_5// "NetBreeze.WidgetList.Header.Description"
0x29ba0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x29ba5  dup
0x29ba6  ldstr    aLocidNetbreeze_6// "LOCID_NETBREEZE_HEAD_PREVIEW"
0x29bab  ldstr    aNetbreezeWidge_6// "NetBreeze.WidgetList.Header.Preview"
0x29bb0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x29bb5  dup
0x29bb6  ldstr    aLocidNetbreeze_7// "LOCID_NETBREEZE_SHOW_FILTERS"
0x29bbb  ldstr    aNetbreezeWidge_7// "NetBreeze.WidgetList.ShowFilters"
0x29bc0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x29bc5  dup
0x29bc6  ldstr    aLocidNetbreeze_8// "LOCID_NETBREEZE_ITEM_CAPTION"
0x29bcb  ldstr    aNetbreezeWidge_8// "NetBreeze.WidgetList.SearchItemCaption"
0x29bd0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x29bd5  dup
0x29bd6  ldstr    aLocidNetbreeze_9// "LOCID_NETBREEZE_ERR_UNSUPPORTED"
0x29bdb  ldstr    aNetbreezeWidge_9// "NetBreeze.WidgetList.Errors.Unsupported"...
0x29be0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x29be5  dup
0x29be6  ldstr    aLocidProcessMo// "LOCID_PROCESS_MOVE"
0x29beb  ldstr    aCommonListedit// "Common.ListEditing.MoveCaptialized"
0x29bf0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x29bf5  dup
0x29bf6  ldstr    aLocidProcessMo_0// "LOCID_PROCESS_MOVE_DOWN"
0x29bfb  ldstr    aCommonListedit_0// "Common.ListEditing.MoveDownCaptialized"
0x29c00  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x29c05  dup
0x29c06  ldstr    aLocidProcessMo_1// "LOCID_PROCESS_MOVE_UP"
0x29c0b  ldstr    aCommonListedit_1// "Common.ListEditing.MoveUpCaptialized"
0x29c10  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x29c15  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SocialInsightControl::localizedStrings
0x29c1a  ret
```
