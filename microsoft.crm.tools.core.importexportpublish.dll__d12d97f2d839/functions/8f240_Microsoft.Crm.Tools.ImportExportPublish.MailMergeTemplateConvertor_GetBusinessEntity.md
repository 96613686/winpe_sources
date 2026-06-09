# Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateConvertor::GetBusinessEntity

- ea: `0x8f240`
- end: `0x8f5d6`
- name: `Microsoft.Crm.Tools.ImportExportPublish.MailMergeTemplateConvertor::GetBusinessEntity`
- size: `918`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8f240`

## string_xrefs

- `0x8f248`: `mailmergetemplateid`
- `0x8f257`: `mailmergetemplateid`
- `0x8f2b2`: `templatetypecode`
- `0x8f2c1`: `templatetypecode`
- `0x8f528`: `parameterxml`
- `0x8f537`: `parameterxml`

## pseudocode

```c

```

## disassembly

```asm
0x8f240  ldarg.1
0x8f241  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.MailMergeTemplate::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8f246  stloc.0
0x8f247  ldarg.2
0x8f248  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x8f24d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f252  stloc.1
0x8f253  ldloc.1
0x8f254  brfalse.s loc_8F271
0x8f256  ldloc.0
0x8f257  ldstr    aMailmergetempl_1// "mailmergetemplateid"
0x8f25c  ldloc.1
0x8f25d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f262  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x8f267  box      [mscorlib]System.Guid
0x8f26c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f271  ldarg.2
0x8f272  ldstr    aName// "name"
0x8f277  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f27c  stloc.1
0x8f27d  ldloc.1
0x8f27e  brfalse.s loc_8F291
0x8f280  ldloc.0
0x8f281  ldstr    aName// "name"
0x8f286  ldloc.1
0x8f287  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f28c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f291  ldarg.2
0x8f292  ldstr    aDescription// "description"
0x8f297  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f29c  stloc.1
0x8f29d  ldloc.1
0x8f29e  brfalse.s loc_8F2B1
0x8f2a0  ldloc.0
0x8f2a1  ldstr    aDescription// "description"
0x8f2a6  ldloc.1
0x8f2a7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f2ac  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f2b1  ldarg.2
0x8f2b2  ldstr    aTemplatetypeco// "templatetypecode"
0x8f2b7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f2bc  stloc.1
0x8f2bd  ldloc.1
0x8f2be  brfalse.s loc_8F2E0
0x8f2c0  ldloc.0
0x8f2c1  ldstr    aTemplatetypeco// "templatetypecode"
0x8f2c6  ldloc.1
0x8f2c7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x8f2cc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8f2d1  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x8f2d6  box      [mscorlib]System.Int32
0x8f2db  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f2e0  ldarg.2
0x8f2e1  ldstr    aMailmergetype// "mailmergetype"
0x8f2e6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f2eb  stloc.1
0x8f2ec  ldloc.1
0x8f2ed  brfalse.s loc_8F30F
0x8f2ef  ldloc.0
0x8f2f0  ldstr    aMailmergetype// "mailmergetype"
0x8f2f5  ldloc.1
0x8f2f6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x8f2fb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8f300  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x8f305  box      [mscorlib]System.Int32
0x8f30a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f30f  ldarg.2
0x8f310  ldstr    aLanguagecode// "languagecode"
0x8f315  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f31a  stloc.1
0x8f31b  ldloc.1
0x8f31c  brfalse.s loc_8F33E
0x8f31e  ldloc.0
0x8f31f  ldstr    aLanguagecode// "languagecode"
0x8f324  ldloc.1
0x8f325  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x8f32a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8f32f  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x8f334  box      [mscorlib]System.Int32
0x8f339  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f33e  ldarg.2
0x8f33f  ldstr    aMimetype// "mimetype"
0x8f344  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f349  stloc.1
0x8f34a  ldloc.1
0x8f34b  brfalse.s loc_8F35E
0x8f34d  ldloc.0
0x8f34e  ldstr    aMimetype// "mimetype"
0x8f353  ldloc.1
0x8f354  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f359  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f35e  ldarg.2
0x8f35f  ldstr    aDocumentformat// "documentformat"
0x8f364  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f369  stloc.1
0x8f36a  ldloc.1
0x8f36b  brfalse.s loc_8F38D
0x8f36d  ldloc.0
0x8f36e  ldstr    aDocumentformat// "documentformat"
0x8f373  ldloc.1
0x8f374  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x8f379  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8f37e  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x8f383  box      [mscorlib]System.Int32
0x8f388  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f38d  ldarg.2
0x8f38e  ldstr    aFilename_0// "filename"
0x8f393  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f398  stloc.1
0x8f399  ldloc.1
0x8f39a  brfalse.s loc_8F3AD
0x8f39c  ldloc.0
0x8f39d  ldstr    aFilename_0// "filename"
0x8f3a2  ldloc.1
0x8f3a3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f3a8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f3ad  ldarg.2
0x8f3ae  ldstr    aBody// "body"
0x8f3b3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f3b8  stloc.1
0x8f3b9  ldloc.1
0x8f3ba  brfalse  loc_8F507
0x8f3bf  ldc.i4.1
0x8f3c0  stloc.2
0x8f3c1  ldloc.1
0x8f3c2  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x8f3c7  brfalse  loc_8F4E3
0x8f3cc  ldloc.1
0x8f3cd  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x8f3d2  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x8f3d7  stloc.3
0x8f3d8  br       loc_8F482
0x8f3dd  ldloc.3
0x8f3de  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8f3e3  castclass [System.Xml]System.Xml.XmlNode
0x8f3e8  stloc.s  4
0x8f3ea  ldloc.s  4
0x8f3ec  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlNode::get_NodeType()
0x8f3f1  ldc.i4.4
0x8f3f2  bne.un   loc_8F482
0x8f3f7  ldloc.s  4
0x8f3f9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f3fe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8f403  brtrue   loc_8F48D
0x8f408  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x8f40d  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetPreamble()
0x8f412  stloc.s  5
0x8f414  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x8f419  ldloc.s  4
0x8f41b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f420  callvirt instance unsigned int8[] [mscorlib]System.Text.Encoding::GetBytes(string)
0x8f425  stloc.s  6
0x8f427  ldloc.s  6
0x8f429  ldlen
0x8f42a  conv.i4
0x8f42b  ldloc.s  5
0x8f42d  ldlen
0x8f42e  conv.i4
0x8f42f  add
0x8f430  newarr   [mscorlib]System.Byte
0x8f435  stloc.s  7
0x8f437  ldloc.s  5
0x8f439  ldc.i4.0
0x8f43a  ldloc.s  7
0x8f43c  ldc.i4.0
0x8f43d  ldloc.s  5
0x8f43f  ldlen
0x8f440  conv.i4
0x8f441  call     void [mscorlib]System.Buffer::BlockCopy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x8f446  ldloc.s  6
0x8f448  ldc.i4.0
0x8f449  ldloc.s  7
0x8f44b  ldloc.s  5
0x8f44d  ldlen
0x8f44e  conv.i4
0x8f44f  ldloc.s  6
0x8f451  ldlen
0x8f452  conv.i4
0x8f453  call     void [mscorlib]System.Buffer::BlockCopy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x8f458  ldloc.0
0x8f459  ldstr    aBody// "body"
0x8f45e  ldloc.s  7
0x8f460  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x8f465  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f46a  ldloc.0
0x8f46b  ldstr    aFilesize// "filesize"
0x8f470  ldloc.s  7
0x8f472  ldlen
0x8f473  conv.i4
0x8f474  box      [mscorlib]System.Int32
0x8f479  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f47e  ldc.i4.0
0x8f47f  stloc.2
0x8f480  leave.s  loc_8F4A3
0x8f482  ldloc.3
0x8f483  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8f488  brtrue   loc_8F3DD
0x8f48d  leave.s  loc_8F4A3
0x8f48f  ldloc.3
0x8f490  isinst   [mscorlib]System.IDisposable
0x8f495  stloc.s  8
0x8f497  ldloc.s  8
0x8f499  brfalse.s loc_8F4A2
0x8f49b  ldloc.s  8
0x8f49d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8f4a2  endfinally
0x8f4a3  ldloc.2
0x8f4a4  brfalse.s loc_8F4E3
0x8f4a6  ldloc.1
0x8f4a7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f4ac  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8f4b1  brtrue.s loc_8F4E3
0x8f4b3  ldloc.0
0x8f4b4  ldstr    aBody// "body"
0x8f4b9  ldloc.1
0x8f4ba  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f4bf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f4c4  ldloc.0
0x8f4c5  ldstr    aFilesize// "filesize"
0x8f4ca  ldloc.1
0x8f4cb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f4d0  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x8f4d5  ldlen
0x8f4d6  conv.i4
0x8f4d7  box      [mscorlib]System.Int32
0x8f4dc  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f4e1  ldc.i4.0
0x8f4e2  stloc.2
0x8f4e3  ldloc.2
0x8f4e4  brfalse.s loc_8F507
0x8f4e6  ldloc.0
0x8f4e7  ldstr    aBody// "body"
0x8f4ec  ldsfld   string [mscorlib]System.String::Empty
0x8f4f1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f4f6  ldloc.0
0x8f4f7  ldstr    aFilesize// "filesize"
0x8f4fc  ldc.i4.0
0x8f4fd  box      [mscorlib]System.Int32
0x8f502  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f507  ldarg.2
0x8f508  ldstr    aDefaultfilter// "defaultfilter"
0x8f50d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f512  stloc.1
0x8f513  ldloc.1
0x8f514  brfalse.s loc_8F527
0x8f516  ldloc.0
0x8f517  ldstr    aDefaultfilter// "defaultfilter"
0x8f51c  ldloc.1
0x8f51d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f522  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f527  ldarg.2
0x8f528  ldstr    aParameterxml// "parameterxml"
0x8f52d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f532  stloc.1
0x8f533  ldloc.1
0x8f534  brfalse.s loc_8F547
0x8f536  ldloc.0
0x8f537  ldstr    aParameterxml// "parameterxml"
0x8f53c  ldloc.1
0x8f53d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f542  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f547  ldloc.0
0x8f548  ldstr    aOwnerid// "ownerid"
0x8f54d  ldarg.1
0x8f54e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x8f553  box      [mscorlib]System.Guid
0x8f558  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f55d  ldloc.0
0x8f55e  ldstr    aOwneridtype// "owneridtype"
0x8f563  ldc.i4.8
0x8f564  box      [mscorlib]System.Int32
0x8f569  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f56e  ldloc.0
0x8f56f  ldstr    aIspersonal// "ispersonal"
0x8f574  ldc.i4.0
0x8f575  box      [mscorlib]System.Boolean
0x8f57a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f57f  ldarg.2
0x8f580  ldstr    aIscustomizable_0// "IsCustomizable"
0x8f585  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f58a  stloc.1
0x8f58b  ldloc.1
0x8f58c  brfalse.s loc_8F5B4
0x8f58e  ldloc.0
0x8f58f  ldstr    aIscustomizable// "iscustomizable"
0x8f594  ldloc.1
0x8f595  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8f59a  ldstr    a1// "1"
0x8f59f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8f5a4  brtrue.s loc_8F5A9
0x8f5a6  ldc.i4.0
0x8f5a7  br.s     loc_8F5AA
0x8f5a9  ldc.i4.1
0x8f5aa  box      [mscorlib]System.Boolean
0x8f5af  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8f5b4  ldarg.2
0x8f5b5  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x8f5ba  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8f5bf  stloc.1
0x8f5c0  ldloc.1
  ... truncated ...
```
