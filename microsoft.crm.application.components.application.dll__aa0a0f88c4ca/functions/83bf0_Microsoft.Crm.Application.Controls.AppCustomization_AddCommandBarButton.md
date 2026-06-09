# Microsoft.Crm.Application.Controls.AppCustomization::AddCommandBarButton

- ea: `0x83bf0`
- end: `0x83e1f`
- name: `Microsoft.Crm.Application.Controls.AppCustomization::AddCommandBarButton`
- size: `559`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x83a90`
- `0x83b90`

## callees

- `0x25700`
- `0x25710`
- `0x25740`
- `0x257e0`
- `0x25800`
- `0x83110`
- `0x83bf0`
- `0x83e20`
- `0x83f40`
- `0x83fa0`
- `0x83fc0`

## string_xrefs

- `0x83c32`: `ValidForCreate`
- `0x83c50`: `ValidForUpdate`
- `0x83d8c`: `AccessKey`

## pseudocode

```c

```

## disassembly

```asm
0x83bf0  ldarg.2
0x83bf1  isinst   [System.Xml]System.Xml.IHasXmlNode
0x83bf6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.IHasXmlNode::GetNode()
0x83bfb  stloc.0
0x83bfc  ldarg.1
0x83bfd  ldloc.0
0x83bfe  ldstr    aClient// "Client"
0x83c03  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x83c08  ldloc.0
0x83c09  ldstr    aAvailableoffli// "AvailableOffline"
0x83c0e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x83c13  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CrmCustomization::ItemIsValidForClient(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.Client, string, string)
0x83c18  brtrue.s loc_83C1C
0x83c1a  ldnull
0x83c1b  ret
0x83c1c  ldarg.s  5
0x83c1e  switch   loc_83C6D, loc_83C31, loc_83C4F
0x83c2f  br.s     loc_83C6D
0x83c31  ldloc.0
0x83c32  ldstr    aValidforcreate// "ValidForCreate"
0x83c37  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x83c3c  stloc.1
0x83c3d  ldloc.1
0x83c3e  brfalse.s loc_83C6D
0x83c40  ldloc.1
0x83c41  ldstr    a1_0// "1"
0x83c46  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x83c4b  brfalse.s loc_83C6D
0x83c4d  ldnull
0x83c4e  ret
0x83c4f  ldloc.0
0x83c50  ldstr    aValidforupdate// "ValidForUpdate"
0x83c55  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x83c5a  stloc.1
0x83c5b  ldloc.1
0x83c5c  brfalse.s loc_83C6D
0x83c5e  ldloc.1
0x83c5f  ldstr    a1_0// "1"
0x83c64  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x83c69  brfalse.s loc_83C6D
0x83c6b  ldnull
0x83c6c  ret
0x83c6d  ldarg.2
0x83c6e  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::get_Name()
0x83c73  ldloc.0
0x83c74  ldstr    aJavascript_1// "JavaScript"
0x83c79  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x83c7e  stloc.2
0x83c7f  ldloc.0
0x83c80  ldstr    aUrl_0// "Url"
0x83c85  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x83c8a  stloc.3
0x83c8b  ldloc.0
0x83c8c  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CrmCustomization::GetLocalizedValue(class [System.Xml]System.Xml.XmlNode)
0x83c91  stloc.s  4
0x83c93  ldsfld   string [mscorlib]System.String::Empty
0x83c98  stloc.s  5
0x83c9a  ldstr    aButton_0// "Button"
0x83c9f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x83ca4  brfalse.s loc_83CB8
0x83ca6  ldloc.0
0x83ca7  ldstr    aTooltips// "ToolTips"
0x83cac  ldstr    aTooltip// "ToolTip"
0x83cb1  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CrmCustomization::GetLocalizedValue(class [System.Xml]System.Xml.XmlNode, string, string)
0x83cb6  stloc.s  5
0x83cb8  newobj   instance void Microsoft.Crm.Application.Menus.OutlookCommandBarButton::.ctor()
0x83cbd  stloc.s  6
0x83cbf  ldloc.3
0x83cc0  brfalse.s loc_83CCA
0x83cc2  ldloc.3
0x83cc3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x83cc8  brtrue.s loc_83CDD
0x83cca  ldloc.2
0x83ccb  brfalse.s loc_83CD5
0x83ccd  ldloc.2
0x83cce  callvirt instance int32 [mscorlib]System.String::get_Length()
0x83cd3  brtrue.s loc_83CDD
0x83cd5  ldstr    aVoid0// "void(0);"
0x83cda  stloc.2
0x83cdb  br.s     loc_83D0B
0x83cdd  ldloc.2
0x83cde  brfalse.s loc_83CE9
0x83ce0  ldloc.2
0x83ce1  callvirt instance int32 [mscorlib]System.String::get_Length()
0x83ce6  ldc.i4.0
0x83ce7  bgt.s    loc_83D0B
0x83ce9  ldarg.s  4
0x83ceb  brfalse.s loc_83D03
0x83ced  ldarg.s  4
0x83cef  callvirt instance int32 [mscorlib]System.String::get_Length()
0x83cf4  ldc.i4.0
0x83cf5  ble.s    loc_83D03
0x83cf7  ldarg.0
0x83cf8  ldarg.2
0x83cf9  ldarg.s  4
0x83cfb  call     instance string Microsoft.Crm.Application.Controls.AppCustomization::BuildIsvActionCmd(class [System.Xml]System.Xml.XPath.XPathNavigator nav, string gridId)
0x83d00  stloc.2
0x83d01  br.s     loc_83D0B
0x83d03  ldarg.0
0x83d04  ldarg.2
0x83d05  call     instance string Microsoft.Crm.Application.Controls.AppCustomization::BuildIsvWinCmd(class [System.Xml]System.Xml.XPath.XPathNavigator nav)
0x83d0a  stloc.2
0x83d0b  ldloc.0
0x83d0c  ldstr    aWinmode// "WinMode"
0x83d11  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x83d16  stloc.s  7
0x83d18  ldloc.s  6
0x83d1a  ldarg.0
0x83d1b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x83d20  ldstr    a012_0// "{0}_{1}_{2}"
0x83d25  ldc.i4.3
0x83d26  newarr   [mscorlib]System.Object
0x83d2b  dup
0x83d2c  ldc.i4.0
0x83d2d  ldarg.0
0x83d2e  call     instance string Microsoft.Crm.Application.Controls.AppCustomization::get_IsvPrefix()
0x83d33  stelem.ref
0x83d34  dup
0x83d35  ldc.i4.1
0x83d36  call     int32 Microsoft.Crm.Application.Controls.AppCustomization::get_NewMenuIndex()
0x83d3b  box      [mscorlib]System.Int32
0x83d40  stelem.ref
0x83d41  dup
0x83d42  ldc.i4.2
0x83d43  ldloc.s  4
0x83d45  stelem.ref
0x83d46  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x83d4b  call     instance string Microsoft.Crm.Application.Controls.AppCustomization::BuildSafeIsvId(string currentId)
0x83d50  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x83d55  ldloc.s  6
0x83d57  ldloc.s  4
0x83d59  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Title(string)
0x83d5e  ldloc.s  6
0x83d60  ldloc.s  5
0x83d62  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_ToolTip(string)
0x83d67  ldloc.s  6
0x83d69  ldloc.2
0x83d6a  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Action(string)
0x83d6f  ldloc.s  6
0x83d71  ldloc.0
0x83d72  ldstr    aIcon// "Icon"
0x83d77  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x83d7c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x83d81  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x83d86  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_Icon(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri)
0x83d8b  ldloc.0
0x83d8c  ldstr    aAccesskey_0// "AccessKey"
0x83d91  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x83d96  stloc.s  8
0x83d98  ldloc.s  6
0x83d9a  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::get_AccessKey()
0x83d9f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x83da4  brfalse.s loc_83DB8
0x83da6  ldloc.s  8
0x83da8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x83dad  brtrue.s loc_83DB8
0x83daf  ldloc.s  6
0x83db1  ldloc.s  8
0x83db3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControl::set_AccessKey(string)
0x83db8  ldloc.s  6
0x83dba  ldloc.s  7
0x83dbc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x83dc1  brtrue.s loc_83DD1
0x83dc3  ldloc.s  7
0x83dc5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x83dca  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x83dcf  br.s     loc_83DD2
0x83dd1  ldc.i4.0
0x83dd2  callvirt instance void Microsoft.Crm.Application.Menus.OutlookCommandBarButton::set_WindowMode(valuetype Microsoft.Crm.Application.Controls.WindowMode value)
0x83dd7  ldloc.s  6
0x83dd9  callvirt instance valuetype Microsoft.Crm.Application.Controls.WindowMode Microsoft.Crm.Application.Menus.OutlookCommandBarButton::get_WindowMode()
0x83dde  brfalse.s loc_83E0E
0x83de0  ldloc.s  6
0x83de2  ldloc.0
0x83de3  ldstr    aUrl_0// "Url"
0x83de8  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x83ded  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x83df2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x83df7  callvirt instance void Microsoft.Crm.Application.Menus.OutlookCommandBarButton::set_WindowUrl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri value)
0x83dfc  ldloc.s  6
0x83dfe  ldloc.0
0x83dff  ldstr    aWinparams// "WinParams"
0x83e04  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::GetStringAttribute(class [System.Xml]System.Xml.XmlNode, string)
0x83e09  callvirt instance void Microsoft.Crm.Application.Menus.OutlookCommandBarButton::set_WindowParameters(string value)
0x83e0e  ldarg.3
0x83e0f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::get_CommandBarControls()
0x83e14  ldloc.s  6
0x83e16  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBarControlCollection::Add(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl)
0x83e1b  pop
0x83e1c  ldloc.s  6
0x83e1e  ret
```
