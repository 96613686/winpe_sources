# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::GetArticleHtml

- ea: `0x19b80`
- end: `0x19d3b`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::GetArticleHtml`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x19770`

## callees

- `0x19b40`
- `0x19b80`

## string_xrefs

- `0x19bf4`: `/combinedxml/articledata/section/content`

## pseudocode

```c

```

## disassembly

```asm
0x19b80  ldarg.0
0x19b81  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::appForm
0x19b86  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x19b8b  ldstr    aStatecode// "statecode"
0x19b90  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19b95  isinst   [mscorlib]System.String
0x19b9a  stloc.0
0x19b9b  ldloc.0
0x19b9c  brfalse.s loc_19BE3
0x19b9e  ldtoken  [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.KbArticleState
0x19ba3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x19ba8  ldloc.0
0x19ba9  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x19bae  unbox.any [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.KbArticleState
0x19bb3  stloc.s  5
0x19bb5  ldc.i4.3
0x19bb6  ldloc.s  5
0x19bb8  bne.un.s loc_19BE3
0x19bba  ldarg.0
0x19bbb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::appForm
0x19bc0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_Entity()
0x19bc5  ldstr    aContent// "content"
0x19bca  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x19bcf  stloc.s  6
0x19bd1  ldloc.s  6
0x19bd3  brtrue.s loc_19BDB
0x19bd5  ldsfld   string [mscorlib]System.String::Empty
0x19bda  ret
0x19bdb  ldloc.s  6
0x19bdd  castclass [mscorlib]System.String
0x19be2  ret
0x19be3  ldarg.0
0x19be4  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::get_CombinedXml()
0x19be9  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x19bee  stloc.1
0x19bef  ldnull
0x19bf0  stloc.2
0x19bf1  ldnull
0x19bf2  stloc.3
0x19bf3  ldloc.1
0x19bf4  ldstr    aCombinedxmlArt// "/combinedxml/articledata/section/conten"...
0x19bf9  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x19bfe  stloc.s  7
0x19c00  ldloc.s  7
0x19c02  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x19c07  stloc.s  8
0x19c09  br.s     loc_19C49
0x19c0b  ldloc.s  8
0x19c0d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x19c12  castclass [System.Xml]System.Xml.XmlNode
0x19c17  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x19c1c  isinst   [System.Xml]System.Xml.XmlCDataSection
0x19c21  stloc.s  9
0x19c23  ldloc.s  9
0x19c25  brfalse.s loc_19C49
0x19c27  ldloc.s  9
0x19c29  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x19c2e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x19c33  ldc.i4.0
0x19c34  ble.s    loc_19C49
0x19c36  ldloc.s  9
0x19c38  ldloc.s  9
0x19c3a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x19c3f  call     string [Microsoft.Crm.SafeHtml]Microsoft.Crm.SafeHtml::GetSafeHtml(string)
0x19c44  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x19c49  ldloc.s  8
0x19c4b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x19c50  brtrue.s loc_19C0B
0x19c52  leave.s  loc_19C75
0x19c54  ldloc.s  8
0x19c56  isinst   [mscorlib]System.IDisposable
0x19c5b  stloc.s  0xA
0x19c5d  ldloc.s  0xA
0x19c5f  brfalse.s loc_19C68
0x19c61  ldloc.s  0xA
0x19c63  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19c68  endfinally
0x19c69  ldloc.s  7
0x19c6b  brfalse.s loc_19C74
0x19c6d  ldloc.s  7
0x19c6f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19c74  endfinally
0x19c75  ldstr    aArticleseditco// "articlesEditContent.xsl"
0x19c7a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x19c7f  call     class [System.Xml]System.Xml.Xsl.XsltArgumentList [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.XmlUtil::GetXslArgumentList(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x19c84  stloc.s  4
0x19c86  ldloc.s  4
0x19c88  ldstr    aTitle// "title"
0x19c8d  ldstr    asc_30804// ""
0x19c92  ldarg.0
0x19c93  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::appForm
0x19c98  ldstr    aTitle// "title"
0x19c9d  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::GetDataValue(string)
0x19ca2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x19ca7  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x19cac  ldloc.s  4
0x19cae  ldstr    aNumber// "number"
0x19cb3  ldstr    asc_30804// ""
0x19cb8  ldarg.0
0x19cb9  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ArticleContentControl::appForm
0x19cbe  ldstr    aNumber// "number"
0x19cc3  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::GetDataValue(string)
0x19cc8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x19ccd  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x19cd2  ldarg.1
0x19cd3  brfalse.s loc_19CEB
0x19cd5  ldloc.s  4
0x19cd7  ldstr    aDesignmode// "designMode"
0x19cdc  ldstr    asc_30804// ""
0x19ce1  ldstr    aTrue// "true"
0x19ce6  callvirt instance void [System.Xml]System.Xml.Xsl.XsltArgumentList::AddParam(string, string, object)
0x19ceb  ldstr    aArticleseditco// "articlesEditContent.xsl"
0x19cf0  call     string [Microsoft.Crm]Microsoft.Crm.ApplicationFileManager::GetApplicationFilePath(string)
0x19cf5  newobj   instance void [System.Xml]System.Xml.XPath.XPathDocument::.ctor(string)
0x19cfa  stloc.2
0x19cfb  newobj   instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::.ctor()
0x19d00  stloc.3
0x19d01  ldloc.3
0x19d02  ldloc.2
0x19d03  ldnull
0x19d04  ldnull
0x19d05  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Load(class [System.Xml]System.Xml.XPath.IXPathNavigable, class [System.Xml]System.Xml.Xsl.XsltSettings, class [System.Xml]System.Xml.XmlResolver)
0x19d0a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19d0f  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x19d14  stloc.s  0xB
0x19d16  ldloc.3
0x19d17  ldloc.1
0x19d18  ldloc.s  4
0x19d1a  ldloc.s  0xB
0x19d1c  callvirt instance void [System.Xml]System.Xml.Xsl.XslCompiledTransform::Transform(class [System.Xml]System.Xml.XPath.IXPathNavigable, class [System.Xml]System.Xml.Xsl.XsltArgumentList, class [mscorlib]System.IO.TextWriter)
0x19d21  ldloc.s  0xB
0x19d23  callvirt instance string [mscorlib]System.Object::ToString()
0x19d28  stloc.s  0xC
0x19d2a  leave.s  loc_19D38
0x19d2c  ldloc.s  0xB
0x19d2e  brfalse.s loc_19D37
0x19d30  ldloc.s  0xB
0x19d32  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19d37  endfinally
0x19d38  ldloc.s  0xC
0x19d3a  ret
```
