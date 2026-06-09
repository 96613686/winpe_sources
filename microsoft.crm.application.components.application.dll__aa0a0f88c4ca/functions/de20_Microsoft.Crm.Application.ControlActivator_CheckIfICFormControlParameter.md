# Microsoft.Crm.Application.ControlActivator::CheckIfICFormControlParameter

- ea: `0xde20`
- end: `0xdec1`
- name: `Microsoft.Crm.Application.ControlActivator::CheckIfICFormControlParameter`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd760`

## callees

- `0xde20`

## string_xrefs

- `0xde5c`: `ReadOnly`
- `0xde94`: `ToolbarJSON`
- `0xdea2`: `ExpandedToolbarJSON`
- `0xdeb0`: `HiddenToolbarJSON`

## pseudocode

```c

```

## disassembly

```asm
0xde20  ldarg.0
0xde21  ldstr    aDisplayascusto// "DisplayAsCustomer360Tile"
0xde26  ldc.i4.5
0xde27  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xde2c  brtrue   loc_DEBD
0xde31  ldarg.0
0xde32  ldstr    aReferencepanel// "ReferencePanelQuickFormCollectionIconUr"...
0xde37  ldc.i4.5
0xde38  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xde3d  brtrue.s loc_DEBD
0xde3f  ldarg.0
0xde40  ldstr    aReferencepanel_0// "ReferencePanelSubgridIconUrl"
0xde45  ldc.i4.5
0xde46  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xde4b  brtrue.s loc_DEBD
0xde4d  ldarg.0
0xde4e  ldstr    aReferencepanel_1// "ReferencePanelSearchWidgetIconUrl"
0xde53  ldc.i4.5
0xde54  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xde59  brtrue.s loc_DEBD
0xde5b  ldarg.0
0xde5c  ldstr    aReadonly// "ReadOnly"
0xde61  ldc.i4.5
0xde62  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xde67  brtrue.s loc_DEBD
0xde69  ldarg.0
0xde6a  ldstr    aShowdialogs// "ShowDialogs"
0xde6f  ldc.i4.5
0xde70  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xde75  brtrue.s loc_DEBD
0xde77  ldarg.0
0xde78  ldstr    aIsviewexpandab// "IsViewExpandable"
0xde7d  ldc.i4.5
0xde7e  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xde83  brtrue.s loc_DEBD
0xde85  ldarg.0
0xde86  ldstr    aHidetoolbar// "HideToolbar"
0xde8b  ldc.i4.5
0xde8c  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xde91  brtrue.s loc_DEBD
0xde93  ldarg.0
0xde94  ldstr    aToolbarjson// "ToolbarJSON"
0xde99  ldc.i4.5
0xde9a  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xde9f  brtrue.s loc_DEBD
0xdea1  ldarg.0
0xdea2  ldstr    aExpandedtoolba// "ExpandedToolbarJSON"
0xdea7  ldc.i4.5
0xdea8  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xdead  brtrue.s loc_DEBD
0xdeaf  ldarg.0
0xdeb0  ldstr    aHiddentoolbarj// "HiddenToolbarJSON"
0xdeb5  ldc.i4.5
0xdeb6  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xdebb  brfalse.s loc_DEBF
0xdebd  ldc.i4.1
0xdebe  ret
0xdebf  ldc.i4.0
0xdec0  ret
```
