# Microsoft.Crm.Application.Utility.LookupMruList::SaveAll

- ea: `0x35ae0`
- end: `0x35cd6`
- name: `Microsoft.Crm.Application.Utility.LookupMruList::SaveAll`
- size: `502`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x11590`
- `0x35460`
- `0x35620`
- `0x356c0`
- `0x358c0`
- `0x35ae0`
- `0x35ce0`
- `0x47920`
- `0x47940`

## string_xrefs

- `0x35c6e`: `Invalid etc found in LookupMruXml: {0}`
- `0x35b02`: `Error Loading the LookupMruXml: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x35ae0  ldnull
0x35ae1  stloc.0
0x35ae2  ldnull
0x35ae3  stloc.1
0x35ae4  ldnull
0x35ae5  stloc.2
0x35ae6  ldarg.0
0x35ae7  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x35aec  stloc.0
0x35aed  leave.s  loc_35B3A
0x35aef  stloc.s  5
0x35af1  ldloc.s  5
0x35af3  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x35af8  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x35afd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35b02  ldstr    aErrorLoadingTh// "Error Loading the LookupMruXml: {0}"
0x35b07  ldc.i4.1
0x35b08  newarr   [mscorlib]System.Object
0x35b0d  dup
0x35b0e  ldc.i4.0
0x35b0f  ldloc.s  5
0x35b11  callvirt instance string [mscorlib]System.Exception::get_Message()
0x35b16  stelem.ref
0x35b17  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x35b1c  ldc.i4.0
0x35b1d  newarr   [mscorlib]System.Object
0x35b22  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x35b27  ldloc.s  5
0x35b29  ldc.i4   0x8004B547
0x35b2e  ldc.i4.0
0x35b2f  newarr   [mscorlib]System.Object
0x35b34  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(class [mscorlib]System.Exception, int32, object[])
0x35b39  throw
0x35b3a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x35b3f  stloc.3
0x35b40  ldloc.0
0x35b41  ldstr    aLookupmrudataL// "/LookupMruData/LookupMruEntityData"
0x35b46  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x35b4b  stloc.s  6
0x35b4d  ldloc.s  6
0x35b4f  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x35b54  stloc.s  7
0x35b56  br.s     loc_35B8C
0x35b58  ldloc.s  7
0x35b5a  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x35b5f  castclass [System.Xml]System.Xml.XmlNode
0x35b64  stloc.s  8
0x35b66  ldloc.3
0x35b67  ldloc.s  8
0x35b69  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x35b6e  ldstr    aEtc// "etc"
0x35b73  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x35b78  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x35b7d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35b82  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x35b87  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x35b8c  ldloc.s  7
0x35b8e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x35b93  brtrue.s loc_35B58
0x35b95  leave.s  loc_35BB8
0x35b97  ldloc.s  7
0x35b99  isinst   [mscorlib]System.IDisposable
0x35b9e  stloc.s  9
0x35ba0  ldloc.s  9
0x35ba2  brfalse.s loc_35BAB
0x35ba4  ldloc.s  9
0x35ba6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35bab  endfinally
0x35bac  ldloc.s  6
0x35bae  brfalse.s loc_35BB7
0x35bb0  ldloc.s  6
0x35bb2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35bb7  endfinally
0x35bb8  ldloc.3
0x35bb9  ldarg.1
0x35bba  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Platform.Entity> Microsoft.Crm.Application.Utility.LookupMruList::loadAllInternal(class [mscorlib]System.Collections.Generic.List`1<int32> etcList, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x35bbf  stloc.2
0x35bc0  ldloc.2
0x35bc1  call     string Microsoft.Crm.Application.Utility.LookupMruList::extractLookupMruFromEntityCollection(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Platform.Entity> entityList)
0x35bc6  stloc.s  4
0x35bc8  ldloc.s  4
0x35bca  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x35bcf  stloc.1
0x35bd0  leave.s  loc_35C12
0x35bd2  stloc.s  0xA
0x35bd4  ldloc.s  0xA
0x35bd6  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x35bdb  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x35be0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35be5  ldstr    aErrorLoadingTh_0// "Error Loading the LookupMru: {0}"
0x35bea  ldc.i4.1
0x35beb  newarr   [mscorlib]System.Object
0x35bf0  dup
0x35bf1  ldc.i4.0
0x35bf2  ldloc.s  0xA
0x35bf4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x35bf9  stelem.ref
0x35bfa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x35bff  ldc.i4.0
0x35c00  newarr   [mscorlib]System.Object
0x35c05  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x35c0a  ldloc.2
0x35c0b  call     void Microsoft.Crm.Application.Utility.LookupMruList::clearLookupMruData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Platform.Entity> entityList)
0x35c10  leave.s  loc_35C12
0x35c12  ldloc.0
0x35c13  ldloc.1
0x35c14  ldarg.1
0x35c15  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Application.Utility.LookupMruList::mergeClientAndServerData(class [System.Xml]System.Xml.XmlDocument clientDoc, class [System.Xml]System.Xml.XmlDocument serverDoc, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x35c1a  ldloc.2
0x35c1b  call     void Microsoft.Crm.Application.Utility.LookupMruList::clearLookupMruData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Platform.Entity> entityList)
0x35c20  ldstr    aLookupmrudataL// "/LookupMruData/LookupMruEntityData"
0x35c25  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x35c2a  stloc.s  0xB
0x35c2c  ldloc.s  0xB
0x35c2e  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x35c33  stloc.s  7
0x35c35  br.s     loc_35CA9
0x35c37  ldloc.s  7
0x35c39  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x35c3e  castclass [System.Xml]System.Xml.XmlNode
0x35c43  stloc.s  0xC
0x35c45  ldc.i4.0
0x35c46  stloc.s  0xD
0x35c48  ldloc.s  0xC
0x35c4a  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x35c4f  ldstr    aEtc// "etc"
0x35c54  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x35c59  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x35c5e  ldc.i4.7
0x35c5f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x35c64  ldloca.s 0xD
0x35c66  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x35c6b  brtrue.s loc_35C99
0x35c6d  ldc.i4.1
0x35c6e  ldstr    aInvalidEtcFoun// "Invalid etc found in LookupMruXml: {0}"
0x35c73  ldc.i4.1
0x35c74  newarr   [mscorlib]System.Object
0x35c79  dup
0x35c7a  ldc.i4.0
0x35c7b  ldloc.s  0xC
0x35c7d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x35c82  ldstr    aEtc// "etc"
0x35c87  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x35c8c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x35c91  stelem.ref
0x35c92  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message, object[] args)
0x35c97  br.s     loc_35CA9
0x35c99  ldloc.s  0xD
0x35c9b  ldloc.s  0xC
0x35c9d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x35ca2  ldloc.2
0x35ca3  ldarg.1
0x35ca4  call     void Microsoft.Crm.Application.Utility.LookupMruList::saveInternal(int32 typeCode, string LookupMruXml, class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Application.Platform.Entity> entityList, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x35ca9  ldloc.s  7
0x35cab  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x35cb0  brtrue.s loc_35C37
0x35cb2  leave.s  loc_35CD5
0x35cb4  ldloc.s  7
0x35cb6  isinst   [mscorlib]System.IDisposable
0x35cbb  stloc.s  9
0x35cbd  ldloc.s  9
0x35cbf  brfalse.s loc_35CC8
0x35cc1  ldloc.s  9
0x35cc3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35cc8  endfinally
0x35cc9  ldloc.s  0xB
0x35ccb  brfalse.s loc_35CD4
0x35ccd  ldloc.s  0xB
0x35ccf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x35cd4  endfinally
0x35cd5  ret
```
