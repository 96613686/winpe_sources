# Word2003XmlFileHandler::ProcessForComment

- ea: `0xa4220`
- end: `0xa44a4`
- name: `Word2003XmlFileHandler::ProcessForComment`
- size: `644`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x11760`
- `0x30260`

## string_xrefs

- `0xa423f`: `http://schemas.microsoft.com/office/word/2003/wordml`
- `0xa4246`: `http://schemas.microsoft.com/office/word/2003/auxHint`
- `0xa422c`: `<aml:annotation aml:id="0" w:type="Word.Comment.Start"/>\n					<w:r><w:t>{0}</w:t></w:r>\n					<aml:annotation aml:id="0" w:type="Word.Comment.End"/>\n					<w:r><w:rPr><w:rStyle w:val="CommentReference"/></w:rPr>\n						<aml:annotation aml:id="0" aml:author="MSCRM" aml:createdate="{1}" w:type="Word.Comment" w:initials="CRM">\n							<aml:content>\n								<w:p>\n									<w:r>\n										<w:t>{2}</w:t>\n									</w:r>\n								</w:p>\n							</aml:content>\n						</aml:annotation>\`
- `0xa42ff`: `MailMerge_Document_Comment_CautionBoldText`
- `0xa4316`: `MailMerge_Document_Comment_CautionText`
- `0xa4381`: `MailMerge_Document_Comment_Text2`
- `0xa441e`: `MailMerge_Document_Comment_Text`
- `0xa4489`: `MailMerge_Document_Comment_BoldText`

## pseudocode

```c

```

## disassembly

```asm
0xa4220  ldstr    aWRWRprWBWRprWT// "<w:r><w:rPr><w:b/></w:rPr><w:t>{0} </w:"...
0xa4225  stloc.0
0xa4226  ldstr    aWRWT0WTWR// "<w:r><w:t>{0}</w:t></w:r>"
0xa422b  stloc.1
0xa422c  ldstr    aAmlAnnotationA// "<aml:annotation aml:id=\"0\" w:type=\"W"...
0xa4231  stloc.2
0xa4232  ldstr    aWRWRprWBWRprWT_0// "<w:r><w:rPr><w:b/></w:rPr><w:t>{0} </w:"...
0xa4237  stloc.3
0xa4238  ldstr    aWPprWPbdrWBott// "<w:pPr><w:pBdr><w:bottom w:val=\"single"...
0xa423d  stloc.s  4
0xa423f  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/office/wor"...
0xa4244  stloc.s  5
0xa4246  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/office/wor"...
0xa424b  stloc.s  6
0xa424d  ldarg.1
0xa424e  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0xa4253  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0xa4258  stloc.s  7
0xa425a  ldloc.s  7
0xa425c  ldstr    aW// "w"
0xa4261  ldloc.s  5
0xa4263  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa4268  ldloc.s  7
0xa426a  ldstr    aWx// "wx"
0xa426f  ldloc.s  6
0xa4271  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0xa4276  ldarg.1
0xa4277  ldstr    aWBody// "//w:body"
0xa427c  ldloc.s  7
0xa427e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0xa4283  stloc.s  8
0xa4285  ldloc.s  8
0xa4287  ldarg.1
0xa4288  ldstr    aWP// "w:p"
0xa428d  ldloc.s  5
0xa428f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa4294  ldloc.s  8
0xa4296  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa429b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa42a0  pop
0xa42a1  ldarg.1
0xa42a2  ldstr    aWP// "w:p"
0xa42a7  ldloc.s  5
0xa42a9  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa42ae  stloc.s  9
0xa42b0  ldloc.s  8
0xa42b2  ldloc.s  9
0xa42b4  ldloc.s  8
0xa42b6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa42bb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa42c0  pop
0xa42c1  ldloc.s  9
0xa42c3  ldloc.s  4
0xa42c5  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0xa42ca  ldarg.1
0xa42cb  ldstr    aWP// "w:p"
0xa42d0  ldloc.s  5
0xa42d2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa42d7  stloc.s  0xA
0xa42d9  ldloc.s  8
0xa42db  ldloc.s  0xA
0xa42dd  ldloc.s  8
0xa42df  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa42e4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa42e9  pop
0xa42ea  ldloc.s  0xA
0xa42ec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa42f1  ldloc.3
0xa42f2  ldc.i4.2
0xa42f3  newarr   [mscorlib]System.Object
0xa42f8  dup
0xa42f9  ldc.i4.0
0xa42fa  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa42ff  ldstr    aMailmergeDocum// "MailMerge_Document_Comment_CautionBoldT"...
0xa4304  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0xa4309  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xa430e  stelem.ref
0xa430f  dup
0xa4310  ldc.i4.1
0xa4311  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa4316  ldstr    aMailmergeDocum_0// "MailMerge_Document_Comment_CautionText"
0xa431b  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0xa4320  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xa4325  stelem.ref
0xa4326  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa432b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0xa4330  ldloc.s  8
0xa4332  ldarg.1
0xa4333  ldstr    aWP// "w:p"
0xa4338  ldloc.s  5
0xa433a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa433f  ldloc.s  8
0xa4341  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa4346  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa434b  pop
0xa434c  ldarg.1
0xa434d  ldstr    aWP// "w:p"
0xa4352  ldloc.s  5
0xa4354  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa4359  stloc.s  0xB
0xa435b  ldloc.s  8
0xa435d  ldloc.s  0xB
0xa435f  ldloc.s  8
0xa4361  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa4366  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa436b  pop
0xa436c  ldloc.s  0xB
0xa436e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa4373  ldloc.2
0xa4374  ldc.i4.3
0xa4375  newarr   [mscorlib]System.Object
0xa437a  dup
0xa437b  ldc.i4.0
0xa437c  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa4381  ldstr    aMailmergeDocum_1// "MailMerge_Document_Comment_Text2"
0xa4386  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0xa438b  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xa4390  stelem.ref
0xa4391  dup
0xa4392  ldc.i4.1
0xa4393  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xa4398  stloc.s  0xE
0xa439a  ldloca.s 0xE
0xa439c  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0xa43a1  stloc.s  0xE
0xa43a3  ldloca.s 0xE
0xa43a5  ldstr    aO// "o"
0xa43aa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa43af  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0xa43b4  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xa43b9  stelem.ref
0xa43ba  dup
0xa43bb  ldc.i4.2
0xa43bc  ldarg.2
0xa43bd  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xa43c2  stelem.ref
0xa43c3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa43c8  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0xa43cd  ldloc.s  8
0xa43cf  ldarg.1
0xa43d0  ldstr    aWP// "w:p"
0xa43d5  ldloc.s  5
0xa43d7  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa43dc  ldloc.s  8
0xa43de  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa43e3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa43e8  pop
0xa43e9  ldarg.1
0xa43ea  ldstr    aWP// "w:p"
0xa43ef  ldloc.s  5
0xa43f1  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa43f6  stloc.s  0xC
0xa43f8  ldloc.s  8
0xa43fa  ldloc.s  0xC
0xa43fc  ldloc.s  8
0xa43fe  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa4403  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa4408  pop
0xa4409  ldloc.s  0xC
0xa440b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa4410  ldloc.1
0xa4411  ldc.i4.1
0xa4412  newarr   [mscorlib]System.Object
0xa4417  dup
0xa4418  ldc.i4.0
0xa4419  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa441e  ldstr    aMailmergeDocum_2// "MailMerge_Document_Comment_Text"
0xa4423  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0xa4428  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xa442d  stelem.ref
0xa442e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa4433  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0xa4438  ldloc.s  8
0xa443a  ldarg.1
0xa443b  ldstr    aWP// "w:p"
0xa4440  ldloc.s  5
0xa4442  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa4447  ldloc.s  8
0xa4449  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa444e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa4453  pop
0xa4454  ldarg.1
0xa4455  ldstr    aWP// "w:p"
0xa445a  ldloc.s  5
0xa445c  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0xa4461  stloc.s  0xD
0xa4463  ldloc.s  8
0xa4465  ldloc.s  0xD
0xa4467  ldloc.s  8
0xa4469  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0xa446e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::InsertBefore(class [System.Xml]System.Xml.XmlNode, class [System.Xml]System.Xml.XmlNode)
0xa4473  pop
0xa4474  ldloc.s  0xD
0xa4476  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa447b  ldloc.0
0xa447c  ldc.i4.1
0xa447d  newarr   [mscorlib]System.Object
0xa4482  dup
0xa4483  ldc.i4.0
0xa4484  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa4489  ldstr    aMailmergeDocum_3// "MailMerge_Document_Comment_BoldText"
0xa448e  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0xa4493  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xa4498  stelem.ref
0xa4499  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa449e  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0xa44a3  ret
```
