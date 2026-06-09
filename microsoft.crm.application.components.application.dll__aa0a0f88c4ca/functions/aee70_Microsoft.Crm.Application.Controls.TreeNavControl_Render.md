# Microsoft.Crm.Application.Controls.TreeNavControl::Render

- ea: `0xaee70`
- end: `0xaefce`
- name: `Microsoft.Crm.Application.Controls.TreeNavControl::Render`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xaede0`
- `0xaee70`

## string_xrefs

- `0xaeef5`: `groupExpandIMGPath`
- `0xaef0b`: `groupCollapseIMGPath`
- `0xaef21`: `nodeExpandIMGPath`
- `0xaef37`: `nodeCollapseIMGPath`
- `0xaef4d`: `nodeBlankIMGPath`

## pseudocode

```c

```

## disassembly

```asm
0xaee70  newobj   instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::.ctor()
0xaee75  stloc.0
0xaee76  newobj   instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::.ctor()
0xaee7b  stloc.1
0xaee7c  ldloc.1
0xaee7d  ldstr    aTreeAltExpand// "Tree.Alt.Expand"
0xaee82  ldsfld   string [mscorlib]System.String::Empty
0xaee87  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xaee8c  ldstr    aTreeAltExpand// "Tree.Alt.Expand"
0xaee91  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaee96  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0xaee9b  ldloc.1
0xaee9c  ldstr    aTreeAltCollaps// "Tree.Alt.Collapse"
0xaeea1  ldsfld   string [mscorlib]System.String::Empty
0xaeea6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xaeeab  ldstr    aTreeAltCollaps// "Tree.Alt.Collapse"
0xaeeb0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xaeeb5  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0xaeeba  ldloc.1
0xaeebb  ldstr    aRtl// "RTL"
0xaeec0  ldsfld   string [mscorlib]System.String::Empty
0xaeec5  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xaeeca  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0xaeecf  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0xaeed4  box      [mscorlib]System.Boolean
0xaeed9  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0xaeede  ldloc.1
0xaeedf  ldstr    aId_1// "id"
0xaeee4  ldsfld   string [mscorlib]System.String::Empty
0xaeee9  ldarg.0
0xaeeea  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0xaeeef  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0xaeef4  ldloc.1
0xaeef5  ldstr    aGroupexpandimg// "groupExpandIMGPath"
0xaeefa  ldsfld   string [mscorlib]System.String::Empty
0xaeeff  ldarg.0
0xaef00  ldfld    string Microsoft.Crm.Application.Controls.TreeNavControl::_groupExpandIMGPath
0xaef05  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0xaef0a  ldloc.1
0xaef0b  ldstr    aGroupcollapsei// "groupCollapseIMGPath"
0xaef10  ldsfld   string [mscorlib]System.String::Empty
0xaef15  ldarg.0
0xaef16  ldfld    string Microsoft.Crm.Application.Controls.TreeNavControl::_groupCollapseIMGPath
0xaef1b  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0xaef20  ldloc.1
0xaef21  ldstr    aNodeexpandimgp// "nodeExpandIMGPath"
0xaef26  ldsfld   string [mscorlib]System.String::Empty
0xaef2b  ldarg.0
0xaef2c  ldfld    string Microsoft.Crm.Application.Controls.TreeNavControl::_nodeExpandIMGPath
0xaef31  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0xaef36  ldloc.1
0xaef37  ldstr    aNodecollapseim// "nodeCollapseIMGPath"
0xaef3c  ldsfld   string [mscorlib]System.String::Empty
0xaef41  ldarg.0
0xaef42  ldfld    string Microsoft.Crm.Application.Controls.TreeNavControl::_nodeCollapseIMGPath
0xaef47  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0xaef4c  ldloc.1
0xaef4d  ldstr    aNodeblankimgpa// "nodeBlankIMGPath"
0xaef52  ldsfld   string [mscorlib]System.String::Empty
0xaef57  ldarg.0
0xaef58  ldfld    string Microsoft.Crm.Application.Controls.TreeNavControl::_nodeBlankIMGPath
0xaef5d  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0xaef62  ldloc.1
0xaef63  ldstr    aDefaultselecte// "defaultSelectedNodeId"
0xaef68  ldsfld   string [mscorlib]System.String::Empty
0xaef6d  ldarg.0
0xaef6e  ldfld    string Microsoft.Crm.Application.Controls.TreeNavControl::_defaultSelectedNodeId
0xaef73  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0xaef78  ldloc.1
0xaef79  ldstr    aDisabled_1// "disabled"
0xaef7e  ldsfld   string [mscorlib]System.String::Empty
0xaef83  ldarg.0
0xaef84  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0xaef89  box      [mscorlib]System.Boolean
0xaef8e  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0xaef93  ldstr    aTreenavXsl// "TreeNav.xsl"
0xaef98  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::LoadXmlDocumentFromFileId(string)
0xaef9d  stloc.2
0xaef9e  ldloc.0
0xaef9f  ldloc.2
0xaefa0  ldnull
0xaefa1  ldnull
0xaefa2  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Load(class [System.Xml]System.Xml.XPath.IXPathNavigable, class [System.Xml]System.Xml.Xsl.XsltSettings, class [System.Xml]System.Xml.XmlResolver)
0xaefa7  ldarg.0
0xaefa8  call     instance string Microsoft.Crm.Application.Controls.TreeNavControl::get_XmlData()
0xaefad  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0xaefb2  stloc.3
0xaefb3  ldloc.0
0xaefb4  ldloc.3
0xaefb5  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0xaefba  ldloc.1
0xaefbb  ldarg.1
0xaefbc  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Transform(class [System.Xml]System.Xml.XmlReader, class [System.Xml]System.Xml.Xsl.XsltArgumentList, class [mscorlib]System.IO.TextWriter)
0xaefc1  leave.s  loc_AEFCD
0xaefc3  ldloc.3
0xaefc4  brfalse.s loc_AEFCC
0xaefc6  ldloc.3
0xaefc7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaefcc  endfinally
0xaefcd  ret
```
