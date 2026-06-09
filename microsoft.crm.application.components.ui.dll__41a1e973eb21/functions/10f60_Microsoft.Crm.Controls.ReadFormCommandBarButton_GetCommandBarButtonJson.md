# Microsoft.Crm.Controls.ReadFormCommandBarButton::GetCommandBarButtonJson

- ea: `0x10f60`
- end: `0x11187`
- name: `Microsoft.Crm.Controls.ReadFormCommandBarButton::GetCommandBarButtonJson`
- size: `551`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x112b0`
- `0x112f0`

## callees

- `0x10760`
- `0x107c0`
- `0x10800`
- `0x10820`
- `0x10f60`
- `0x116f0`
- `0x11710`
- `0x11740`
- `0x11800`
- `0x1a3c0`
- `0x1a3f0`
- `0x1a400`
- `0x1a540`
- `0x1a610`
- `0x23c20`
- `0x241c0`
- `0x24210`

## pseudocode

```c

```

## disassembly

```asm
0x10f60  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x10f65  stloc.0
0x10f66  ldloc.0
0x10f67  ldstr    asc_4889A// "{"
0x10f6c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10f71  pop
0x10f72  ldloc.0
0x10f73  ldstr    aTitle_5// "\"Title\":"
0x10f78  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10f7d  pop
0x10f7e  ldloc.0
0x10f7f  ldarg.0
0x10f80  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x10f85  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x10f8a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10f8f  pop
0x10f90  ldloc.0
0x10f91  ldstr    asc_2B428// ","
0x10f96  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10f9b  pop
0x10f9c  ldloc.0
0x10f9d  ldstr    aTooltip_1// "\"ToolTip\":"
0x10fa2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10fa7  pop
0x10fa8  ldloc.0
0x10fa9  ldarg.0
0x10faa  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0x10faf  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x10fb4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10fb9  pop
0x10fba  ldloc.0
0x10fbb  ldstr    asc_2B428// ","
0x10fc0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10fc5  pop
0x10fc6  ldloc.0
0x10fc7  ldstr    aAction_1// "\"Action\":"
0x10fcc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10fd1  pop
0x10fd2  ldloc.0
0x10fd3  ldarg.0
0x10fd4  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Action()
0x10fd9  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x10fde  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10fe3  pop
0x10fe4  ldloc.0
0x10fe5  ldstr    asc_2B428// ","
0x10fea  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10fef  pop
0x10ff0  ldloc.0
0x10ff1  ldstr    aIstrimmed_0// "\"IsTrimmed\":"
0x10ff6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x10ffb  pop
0x10ffc  ldloc.0
0x10ffd  ldarg.0
0x10ffe  call     instance bool Microsoft.Crm.Controls.ReadFormCommandBarButton::get_IsTrimmed()
0x11003  box      [mscorlib]System.Boolean
0x11008  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x1100d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11012  pop
0x11013  ldloc.0
0x11014  ldstr    asc_2B428// ","
0x11019  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1101e  pop
0x1101f  ldloc.0
0x11020  ldstr    aVisibilityrule_0// "\"VisibilityRules\":"
0x11025  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1102a  pop
0x1102b  ldloc.0
0x1102c  ldstr    asc_2B428// ","
0x11031  ldarg.0
0x11032  call     instance int32[] Microsoft.Crm.Controls.ReadFormCommandBarButton::get_VisibilityRules()
0x11037  ldsfld   class [mscorlib]System.Func`2<int32, string> <>c::<>9__52_0
0x1103c  dup
0x1103d  brtrue.s loc_11056
0x1103f  pop
0x11040  ldsfld   class <>c <>c::<>9
0x11045  ldftn    instance string <>c::<GetCommandBarButtonJson>b__52_0(int32 visibilityRule)
0x1104b  newobj   instance void class [mscorlib]System.Func`2<int32, string>::.ctor(object, native int)
0x11050  dup
0x11051  stsfld   class [mscorlib]System.Func`2<int32, string> <>c::<>9__52_0
0x11056  call     T0x2B00001A
0x1105b  call     T0x2B000003
0x11060  call     string [mscorlib]System.String::Join(string, string[])
0x11065  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x1106a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1106f  pop
0x11070  ldarg.0
0x11071  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.CommandBarControl::get_Icon()
0x11076  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::IsEmpty()
0x1107b  brtrue   loc_11174
0x11080  ldstr    asc_3280A// ""
0x11085  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1108a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1108f  ldc.i4.0
0x11090  newobj   instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri source, bool includeControlsCss)
0x11095  stloc.1
0x11096  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x1109b  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x110a0  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x110a5  stloc.2
0x110a6  ldstr    aFirst// "First"
0x110ab  stloc.3
0x110ac  ldarg.0
0x110ad  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_Title()
0x110b2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x110b7  brfalse.s loc_110D2
0x110b9  ldarg.0
0x110ba  call     instance bool Microsoft.Crm.Controls.ReadFormCommandBarButton::get_DownArrow()
0x110bf  brfalse.s loc_110D2
0x110c1  ldloc.2
0x110c2  brfalse.s loc_110CC
0x110c4  ldstr    aRtl_0// "RTL"
0x110c9  stloc.3
0x110ca  br.s     loc_110D2
0x110cc  ldstr    aLtr_0// "LTR"
0x110d1  stloc.3
0x110d2  ldloc.1
0x110d3  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::ClearExpando()
0x110d8  ldloc.1
0x110d9  ldarg.0
0x110da  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Controls.CommandBarControl::get_Icon()
0x110df  callvirt instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::set_Source(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri value)
0x110e4  ldloc.1
0x110e5  ldstr    aAlt// "alt"
0x110ea  ldarg.0
0x110eb  callvirt instance string Microsoft.Crm.Controls.CommandBarControl::get_ToolTip()
0x110f0  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x110f5  ldloc.1
0x110f6  ldstr    aTabindex_0// "tabIndex"
0x110fb  ldstr    a1_0// "-1"
0x11100  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x11105  ldarg.0
0x11106  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1110b  brfalse.s loc_11120
0x1110d  ldloc.1
0x1110e  ldstr    aMsCrmMenuButto_1// "ms-crm-Menu-Button-disabled ms-crm-Menu"...
0x11113  ldloc.3
0x11114  call     string [mscorlib]System.String::Concat(string, string)
0x11119  callvirt instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::set_CssClass(string value)
0x1111e  br.s     loc_11131
0x11120  ldloc.1
0x11121  ldstr    aMsCrmMenuButto_0// "ms-crm-Menu-Button"
0x11126  ldloc.3
0x11127  call     string [mscorlib]System.String::Concat(string, string)
0x1112c  callvirt instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::set_CssClass(string value)
0x11131  ldarg.0
0x11132  call     instance bool Microsoft.Crm.Controls.ReadFormCommandBarButton::get_FlipImageInRightToLeft()
0x11137  brfalse.s loc_1114F
0x11139  ldloc.1
0x1113a  dup
0x1113b  callvirt instance string Microsoft.Crm.Application.Components.UI.ImageStripImage::get_CssClass()
0x11140  ldstr    aMsCrmRtlFlip// " ms-crm-RTL-Flip"
0x11145  call     string [mscorlib]System.String::Concat(string, string)
0x1114a  callvirt instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::set_CssClass(string value)
0x1114f  ldloc.0
0x11150  ldstr    asc_2B428// ","
0x11155  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1115a  pop
0x1115b  ldloc.0
0x1115c  ldloc.1
0x1115d  callvirt instance string Microsoft.Crm.Application.Components.UI.ImageStripImage::get_ImageJsonData()
0x11162  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x11167  pop
0x11168  leave.s  loc_11174
0x1116a  ldloc.1
0x1116b  brfalse.s loc_11173
0x1116d  ldloc.1
0x1116e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11173  endfinally
0x11174  ldloc.0
0x11175  ldstr    asc_3BC36// "}"
0x1117a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x1117f  pop
0x11180  ldloc.0
0x11181  callvirt instance string [mscorlib]System.Object::ToString()
0x11186  ret
```
