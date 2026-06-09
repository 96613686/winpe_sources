# Microsoft.Crm.Application.Controls.TreeNavControl::RegisterAjaxComponent

- ea: `0xaece0`
- end: `0xaedd4`
- name: `Microsoft.Crm.Application.Controls.TreeNavControl::RegisterAjaxComponent`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xaee00`

## string_xrefs

- `0xaedb5`: `leftNavBreadcrumbImg`
- `0xaed41`: `nav_components`
- `0xaece7`: `groupExpandIMGPath`
- `0xaecf8`: `groupCollapseIMGPath`
- `0xaed09`: `nodeExpandIMGPath`
- `0xaed1a`: `nodeCollapseIMGPath`
- `0xaed3c`: `treeNavComponentId`
- `0xaed80`: `breadcrumbLargeIconImgId`
- `0xaed85`: `BreadcrumbLargeIconImg`
- `0xaeda0`: `leftNavBreadcrumbTextId`
- `0xaeda5`: `leftNavBreadcrumbText`
- `0xaedb0`: `leftNavBreadcrumbImgId`

## pseudocode

```c

```

## disassembly

```asm
0xaece0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0xaece5  stloc.0
0xaece6  ldloc.0
0xaece7  ldstr    aGroupexpandimg// "groupExpandIMGPath"
0xaecec  ldarg.0
0xaeced  ldfld    string Microsoft.Crm.Application.Controls.TreeNavControl::_groupExpandIMGPath
0xaecf2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xaecf7  ldloc.0
0xaecf8  ldstr    aGroupcollapsei// "groupCollapseIMGPath"
0xaecfd  ldarg.0
0xaecfe  ldfld    string Microsoft.Crm.Application.Controls.TreeNavControl::_groupCollapseIMGPath
0xaed03  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xaed08  ldloc.0
0xaed09  ldstr    aNodeexpandimgp// "nodeExpandIMGPath"
0xaed0e  ldarg.0
0xaed0f  ldfld    string Microsoft.Crm.Application.Controls.TreeNavControl::_nodeExpandIMGPath
0xaed14  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xaed19  ldloc.0
0xaed1a  ldstr    aNodecollapseim// "nodeCollapseIMGPath"
0xaed1f  ldarg.0
0xaed20  ldfld    string Microsoft.Crm.Application.Controls.TreeNavControl::_nodeCollapseIMGPath
0xaed25  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xaed2a  ldloc.0
0xaed2b  ldstr    aDefaultselecte// "defaultSelectedNodeId"
0xaed30  ldarg.0
0xaed31  ldfld    string Microsoft.Crm.Application.Controls.TreeNavControl::_defaultSelectedNodeId
0xaed36  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xaed3b  ldloc.0
0xaed3c  ldstr    aTreenavcompone// "treeNavComponentId"
0xaed41  ldstr    aNavComponents// "nav_components"
0xaed46  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xaed4b  ldloc.0
0xaed4c  ldstr    aLabelcollapsed// "labelCollapsed"
0xaed51  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xaed56  ldstr    aTreeAltExpand// "Tree.Alt.Expand"
0xaed5b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaed60  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xaed65  ldloc.0
0xaed66  ldstr    aLabelexpanded// "labelExpanded"
0xaed6b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xaed70  ldstr    aTreeAltCollaps// "Tree.Alt.Collapse"
0xaed75  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaed7a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xaed7f  ldloc.0
0xaed80  ldstr    aBreadcrumblarg// "breadcrumbLargeIconImgId"
0xaed85  ldstr    aBreadcrumblarg_0// "BreadcrumbLargeIconImg"
0xaed8a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xaed8f  ldloc.0
0xaed90  ldstr    aFormTitleSpani// "form_title_spanId"
0xaed95  ldstr    aFormTitleSpan// "form_title_span"
0xaed9a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xaed9f  ldloc.0
0xaeda0  ldstr    aLeftnavbreadcr_0// "leftNavBreadcrumbTextId"
0xaeda5  ldstr    aLeftnavbreadcr_1// "leftNavBreadcrumbText"
0xaedaa  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xaedaf  ldloc.0
0xaedb0  ldstr    aLeftnavbreadcr_2// "leftNavBreadcrumbImgId"
0xaedb5  ldstr    aLeftnavbreadcr// "leftNavBreadcrumbImg"
0xaedba  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0xaedbf  ldarg.0
0xaedc0  ldstr    aMscrmTreenavco// "Mscrm.TreeNavControl"
0xaedc5  ldloc.0
0xaedc6  ldnull
0xaedc7  ldnull
0xaedc8  ldarg.0
0xaedc9  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xaedce  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string)
0xaedd3  ret
```
