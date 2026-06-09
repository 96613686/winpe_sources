# Microsoft.Crm.Application.Controls.AppCustomization::CustomizeMenuBar

- ea: `0x838a0`
- end: `0x839e2`
- name: `Microsoft.Crm.Application.Controls.AppCustomization::CustomizeMenuBar`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x17d60`

## callees

- `0x83110`
- `0x838a0`
- `0x83a90`

## string_xrefs

- `0x838b4`: `configuration/`
- `0x838f4`: `ValidForCreate`
- `0x8391f`: `ValidForUpdate`
- `0x83950`: `AccessKey`

## pseudocode

```c

```

## disassembly

```asm
0x838a0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x838a5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CrmCustomization::IsvIntegrationOn(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x838aa  brfalse  loc_839E1
0x838af  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CrmCustomization::get_IsvXml()
0x838b4  ldstr    aConfiguration// "configuration/"
0x838b9  ldarg.3
0x838ba  ldstr    aMenu_2// "/Menu"
0x838bf  call     string [mscorlib]System.String::Concat(string, string, string)
0x838c4  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x838c9  stloc.1
0x838ca  ldc.i4.0
0x838cb  stloc.2
0x838cc  br       loc_839C9
0x838d1  ldloc.1
0x838d2  ldloc.2
0x838d3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x838d8  stloc.3
0x838d9  ldarg.s  4
0x838db  switch   loc_83942, loc_838EE, loc_83919
0x838ec  br.s     loc_83942
0x838ee  ldloc.3
0x838ef  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x838f4  ldstr    aValidforcreate// "ValidForCreate"
0x838f9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x838fe  stloc.0
0x838ff  ldloc.0
0x83900  brfalse.s loc_83942
0x83902  ldloc.0
0x83903  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x83908  ldstr    a1_0// "1"
0x8390d  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x83912  brfalse.s loc_83942
0x83914  br       loc_839C5
0x83919  ldloc.3
0x8391a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x8391f  ldstr    aValidforupdate// "ValidForUpdate"
0x83924  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x83929  stloc.0
0x8392a  ldloc.0
0x8392b  brfalse.s loc_83942
0x8392d  ldloc.0
0x8392e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x83933  ldstr    a1_0// "1"
0x83938  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x8393d  brtrue   loc_839C5
0x83942  ldloc.3
0x83943  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CrmCustomization::GetLocalizedValue(class [System.Xml]System.Xml.XmlNode)
0x83948  stloc.s  4
0x8394a  ldloc.3
0x8394b  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x83950  ldstr    aAccesskey_0// "AccessKey"
0x83955  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x8395a  stloc.s  5
0x8395c  ldloc.s  5
0x8395e  brfalse.s loc_83969
0x83960  ldloc.s  5
0x83962  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x83967  br.s     loc_8396A
0x83969  ldnull
0x8396a  stloc.s  6
0x8396c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x83971  ldstr    a012_0// "{0}_{1}_{2}"
0x83976  ldc.i4.3
0x83977  newarr   [mscorlib]System.Object
0x8397c  dup
0x8397d  ldc.i4.0
0x8397e  ldarg.0
0x8397f  call     instance string Microsoft.Crm.Application.Controls.AppCustomization::get_IsvPrefix()
0x83984  stelem.ref
0x83985  dup
0x83986  ldc.i4.1
0x83987  ldloc.2
0x83988  box      [mscorlib]System.Int32
0x8398d  stelem.ref
0x8398e  dup
0x8398f  ldc.i4.2
0x83990  ldloc.s  4
0x83992  stelem.ref
0x83993  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x83998  stloc.s  7
0x8399a  ldarg.2
0x8399b  ldind.ref
0x8399c  ldloc.s  4
0x8399e  ldloc.s  7
0x839a0  ldloc.s  6
0x839a2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::CreateMenu(string, string, string)
0x839a7  stloc.s  8
0x839a9  ldarg.0
0x839aa  ldarg.1
0x839ab  ldloc.3
0x839ac  callvirt instance class [System.Xml]System.Xml.XPath.XPathNavigator [System.Xml]System.Xml.XmlNode::CreateNavigator()
0x839b1  ldarg.2
0x839b2  ldloca.s 8
0x839b4  ldnull
0x839b5  ldarg.s  4
0x839b7  call     instance void Microsoft.Crm.Application.Controls.AppCustomization::AddItemsToMenuBar(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.Client client, class [System.Xml]System.Xml.XPath.XPathNavigator nav, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar& menuBar, class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu& currentMenu, string gridId, valuetype Microsoft.Crm.Application.Forms.FormState formState)
0x839bc  ldarg.2
0x839bd  ldind.ref
0x839be  ldloc.s  8
0x839c0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::AddMenu(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu)
0x839c5  ldloc.2
0x839c6  ldc.i4.1
0x839c7  add
0x839c8  stloc.2
0x839c9  ldloc.2
0x839ca  ldloc.1
0x839cb  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x839d0  blt      loc_838D1
0x839d5  leave.s  loc_839E1
0x839d7  ldloc.1
0x839d8  brfalse.s loc_839E0
0x839da  ldloc.1
0x839db  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x839e0  endfinally
0x839e1  ret
```
