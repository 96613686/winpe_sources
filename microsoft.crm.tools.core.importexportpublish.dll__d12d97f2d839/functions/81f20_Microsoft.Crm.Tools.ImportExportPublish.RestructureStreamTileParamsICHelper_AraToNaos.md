# Microsoft.Crm.Tools.ImportExportPublish.RestructureStreamTileParamsICHelper::AraToNaos

- ea: `0x81f20`
- end: `0x82467`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RestructureStreamTileParamsICHelper::AraToNaos`
- size: `1351`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x25dd0`

## callees

- `0x81f20`
- `0x82470`
- `0x82490`
- `0x824b0`
- `0x824e0`

## string_xrefs

- `0x820b7`: `Restructuring Interaction Centric Dashboard form xml: Processing stream/tile parameters at {0} for control with ID {1}`
- `0x820f2`: `Invalid Interaction Centric Dashboard form xml. Could not find child node ShowAsTiles at {0} for control with ID {1}`
- `0x8219d`: `Restructuring stream {0}`
- `0x821e8`: `Invalid stream format "{0}" in Interaction Centric Dashboard form xml at {1} for control with ID {2}`
- `0x822be`: `Invalid stream format "{0}" in Interaction Centric Dashboard form xml at {1} for control with ID {2}`
- `0x82359`: `Invalid stream format "{0}" in Interaction Centric Dashboard form xml at {1} for control with ID {2}`
- `0x823b0`: `Invalid stream format "{0}" in Interaction Centric Dashboard form xml at {1} for control with ID {2} Found unrecognised stream type ' {3} '`
- `0x823e4`: `Restructuring stream {0} complete`

## pseudocode

```c

```

## disassembly

```asm
0x81f20  ldc.i4.0
0x81f21  stloc.0
0x81f22  ldarg.0
0x81f23  ldarg.2
0x81f24  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x81f29  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x81f2e  stloc.1
0x81f2f  br       loc_81FE4
0x81f34  ldloc.1
0x81f35  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x81f3a  castclass [System.Xml]System.Xml.XmlElement
0x81f3f  stloc.2
0x81f40  ldloc.2
0x81f41  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x81f46  brfalse  loc_81FE4
0x81f4b  ldloc.2
0x81f4c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x81f51  ldstr    aPrimaryentityl_0// "primaryentitylogicalname"
0x81f56  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x81f5b  brtrue   loc_81FE4
0x81f60  ldstr    a0_1// "0"
0x81f65  stloc.3
0x81f66  ldloc.2
0x81f67  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x81f6c  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x81f71  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x81f76  brfalse.s loc_81F99
0x81f78  ldloc.2
0x81f79  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x81f7e  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x81f83  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x81f88  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x81f8d  stloc.3
0x81f8e  ldloc.2
0x81f8f  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x81f94  callvirt instance void [System.Xml]System.Xml.XmlElement::RemoveAttribute(string)
0x81f99  ldloc.3
0x81f9a  ldloca.s 4
0x81f9c  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x81fa1  pop
0x81fa2  ldloc.s  4
0x81fa4  ldarg.3
0x81fa5  call     string Microsoft.Crm.Tools.ImportExportPublish.RestructureStreamTileParamsICHelper::GetEntityLogicalName(int32 otc, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x81faa  stloc.s  5
0x81fac  ldloc.2
0x81fad  ldstr    aPrimaryentityl_0// "primaryentitylogicalname"
0x81fb2  ldloc.s  5
0x81fb4  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x81fb9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x81fbe  ldstr    aChangedPrimary// "Changed primaryentitytypecode=\"{0}\" t"...
0x81fc3  ldc.i4.2
0x81fc4  newarr   [mscorlib]System.Object
0x81fc9  dup
0x81fca  ldc.i4.0
0x81fcb  ldloc.3
0x81fcc  stelem.ref
0x81fcd  dup
0x81fce  ldc.i4.1
0x81fcf  ldloc.s  5
0x81fd1  stelem.ref
0x81fd2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x81fd7  ldc.i4.0
0x81fd8  newarr   [mscorlib]System.Object
0x81fdd  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::Write(string, object[])
0x81fe2  ldc.i4.1
0x81fe3  stloc.0
0x81fe4  ldloc.1
0x81fe5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x81fea  brtrue   loc_81F34
0x81fef  leave.s  loc_82005
0x81ff1  ldloc.1
0x81ff2  isinst   [mscorlib]System.IDisposable
0x81ff7  stloc.s  6
0x81ff9  ldloc.s  6
0x81ffb  brfalse.s loc_82004
0x81ffd  ldloc.s  6
0x81fff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x82004  endfinally
0x82005  ldarg.0
0x82006  ldarg.1
0x82007  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x8200c  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x82011  stloc.1
0x82012  br       loc_82444
0x82017  ldloc.1
0x82018  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8201d  castclass [System.Xml]System.Xml.XmlNode
0x82022  stloc.s  7
0x82024  ldloc.s  7
0x82026  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8202b  brfalse  loc_82444
0x82030  ldloc.s  7
0x82032  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x82037  ldstr    aParameters// "parameters"
0x8203c  callvirt instance bool [mscorlib]System.String::Equals(string)
0x82041  brfalse  loc_82444
0x82046  ldloc.s  7
0x82048  ldstr    aStreams// "Streams"
0x8204d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x82052  stloc.s  8
0x82054  ldloc.s  8
0x82056  brfalse  loc_82444
0x8205b  ldstr    aUnknown// "unknown"
0x82060  stloc.s  9
0x82062  ldloc.s  7
0x82064  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x82069  brfalse.s loc_820AE
0x8206b  ldloc.s  7
0x8206d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x82072  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x82077  brfalse.s loc_820AE
0x82079  ldloc.s  7
0x8207b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x82080  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x82085  ldstr    aId// "id"
0x8208a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x8208f  brfalse.s loc_820AE
0x82091  ldloc.s  7
0x82093  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x82098  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x8209d  ldstr    aId// "id"
0x820a2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x820a7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x820ac  stloc.s  9
0x820ae  ldarg.s  4
0x820b0  brfalse.s loc_820DB
0x820b2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x820b7  ldstr    aRestructuringI// "Restructuring Interaction Centric Dashb"...
0x820bc  ldc.i4.2
0x820bd  newarr   [mscorlib]System.Object
0x820c2  dup
0x820c3  ldc.i4.0
0x820c4  ldarg.1
0x820c5  stelem.ref
0x820c6  dup
0x820c7  ldc.i4.1
0x820c8  ldloc.s  9
0x820ca  stelem.ref
0x820cb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x820d0  ldc.i4.0
0x820d1  newarr   [mscorlib]System.Object
0x820d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::Write(string, object[])
0x820db  ldloc.s  7
0x820dd  ldstr    aShowastiles// "ShowAsTiles"
0x820e2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x820e7  stloc.s  0xA
0x820e9  ldloc.s  0xA
0x820eb  brtrue.s loc_82111
0x820ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x820f2  ldstr    aInvalidInterac// "Invalid Interaction Centric Dashboard f"...
0x820f7  ldc.i4.2
0x820f8  newarr   [mscorlib]System.Object
0x820fd  dup
0x820fe  ldc.i4.0
0x820ff  ldarg.1
0x82100  stelem.ref
0x82101  dup
0x82102  ldc.i4.1
0x82103  ldloc.s  9
0x82105  stelem.ref
0x82106  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8210b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x82110  throw
0x82111  ldloc.s  0xA
0x82113  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x82118  stloc.s  0xB
0x8211a  ldloc.s  8
0x8211c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x82121  ldc.i4.1
0x82122  newarr   [mscorlib]System.Char
0x82127  dup
0x82128  ldc.i4.0
0x82129  ldc.i4.s 0x3B
0x8212b  stelem.i2
0x8212c  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x82131  ldloc.s  7
0x82133  callvirt instance void [System.Xml]System.Xml.XmlNode::RemoveAll()
0x82138  ldarg.0
0x82139  ldstr    aStreamobjects// "StreamObjects"
0x8213e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x82143  stloc.s  0xC
0x82145  ldloc.s  7
0x82147  ldloc.s  0xC
0x82149  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x8214e  pop
0x8214f  ldloc.s  0xB
0x82151  ldstr    a1// "1"
0x82156  callvirt instance bool [mscorlib]System.String::Equals(string)
0x8215b  brfalse.s loc_82171
0x8215d  ldarg.0
0x8215e  ldstr    aShowastiles// "ShowAsTiles"
0x82163  ldstr    aTrue// "true"
0x82168  ldloc.s  0xC
0x8216a  call     void Microsoft.Crm.Tools.ImportExportPublish.RestructureStreamTileParamsICHelper::CreateAndAppendXmlNode(class [System.Xml]System.Xml.XmlDocument xmlDoc, string nodeName, string innerText, class [System.Xml]System.Xml.XmlNode parentNode)
0x8216f  br.s     loc_82183
0x82171  ldarg.0
0x82172  ldstr    aShowastiles// "ShowAsTiles"
0x82177  ldstr    aFalse// "false"
0x8217c  ldloc.s  0xC
0x8217e  call     void Microsoft.Crm.Tools.ImportExportPublish.RestructureStreamTileParamsICHelper::CreateAndAppendXmlNode(class [System.Xml]System.Xml.XmlDocument xmlDoc, string nodeName, string innerText, class [System.Xml]System.Xml.XmlNode parentNode)
0x82183  stloc.s  0xD
0x82185  ldc.i4.0
0x82186  stloc.s  0xE
0x82188  br       loc_8240A
0x8218d  ldloc.s  0xD
0x8218f  ldloc.s  0xE
0x82191  ldelem.ref
0x82192  stloc.s  0xF
0x82194  ldarg.s  4
0x82196  brfalse.s loc_821BD
0x82198  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8219d  ldstr    aRestructuringS// "Restructuring stream {0}"
0x821a2  ldc.i4.1
0x821a3  newarr   [mscorlib]System.Object
0x821a8  dup
0x821a9  ldc.i4.0
0x821aa  ldloc.s  0xF
0x821ac  stelem.ref
0x821ad  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x821b2  ldc.i4.0
0x821b3  newarr   [mscorlib]System.Object
0x821b8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::Write(string, object[])
0x821bd  ldloc.s  0xF
0x821bf  ldc.i4.1
0x821c0  newarr   [mscorlib]System.Char
0x821c5  dup
0x821c6  ldc.i4.0
0x821c7  ldc.i4.s 0x7C
0x821c9  stelem.i2
0x821ca  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x821cf  stloc.s  0x10
0x821d1  ldloc.s  0x10
0x821d3  ldc.i4.0
0x821d4  ldelem.ref
0x821d5  brfalse.s loc_821E3
0x821d7  ldloc.s  0x10
0x821d9  ldc.i4.1
0x821da  ldelem.ref
0x821db  brfalse.s loc_821E3
0x821dd  ldloc.s  0x10
0x821df  ldc.i4.2
0x821e0  ldelem.ref
0x821e1  brtrue.s loc_8220C
0x821e3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x821e8  ldstr    aInvalidStreamF// "Invalid stream format \"{0}\" in Intera"...
0x821ed  ldc.i4.3
0x821ee  newarr   [mscorlib]System.Object
0x821f3  dup
0x821f4  ldc.i4.0
0x821f5  ldloc.s  0xF
0x821f7  stelem.ref
0x821f8  dup
0x821f9  ldc.i4.1
0x821fa  ldarg.1
0x821fb  stelem.ref
0x821fc  dup
0x821fd  ldc.i4.2
0x821fe  ldloc.s  9
0x82200  stelem.ref
0x82201  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x82206  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x8220b  throw
0x8220c  ldarg.0
0x8220d  ldstr    aStreamobject// "StreamObject"
0x82212  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x82217  stloc.s  0x11
0x82219  ldloc.s  0x11
0x8221b  ldstr    aType_0// "type"
0x82220  ldloc.s  0x10
0x82222  ldc.i4.0
0x82223  ldelem.ref
0x82224  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x82229  ldloc.s  0x11
0x8222b  ldstr    aId// "id"
0x82230  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x82235  stloc.s  0x14
0x82237  ldloca.s 0x14
0x82239  constrained. [mscorlib]System.Guid
0x8223f  callvirt instance string [mscorlib]System.Object::ToString()
0x82244  call     string Microsoft.Crm.Tools.ImportExportPublish.RestructureStreamTileParamsICHelper::ParanthesizeString(string s)
0x82249  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0x8224e  ldloc.s  0xC
0x82250  ldloc.s  0x11
0x82252  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x82257  pop
0x82258  ldloc.s  0x10
0x8225a  ldc.i4.2
0x8225b  ldelem.ref
0x8225c  ldloca.s 0x12
0x8225e  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x82263  pop
0x82264  ldloc.s  0x10
0x82266  ldc.i4.0
0x82267  ldelem.ref
0x82268  ldstr    a1// "1"
0x8226d  callvirt instance bool [mscorlib]System.String::Equals(string)
0x82272  brtrue.s loc_8227E
0x82274  ldloc.s  0x12
0x82276  ldarg.3
0x82277  call     string Microsoft.Crm.Tools.ImportExportPublish.RestructureStreamTileParamsICHelper::GetEntityLogicalName(int32 otc, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
  ... truncated ...
```
