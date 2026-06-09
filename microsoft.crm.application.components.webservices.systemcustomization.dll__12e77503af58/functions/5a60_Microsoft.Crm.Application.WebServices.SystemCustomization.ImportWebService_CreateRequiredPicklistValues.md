# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateRequiredPicklistValues

- ea: `0x5a60`
- end: `0x5d1a`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateRequiredPicklistValues`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x57e0`

## callees

- `0x5a20`
- `0x5a60`
- `0x6740`

## pseudocode

```c

```

## disassembly

```asm
0x5a60  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5a65  stloc.0
0x5a66  ldarg.1
0x5a67  ldstr    aMapEntitymapsE_0// "/Map/EntityMaps/EntityMap[not(@Unused) "...
0x5a6c  ldc.i4.2
0x5a6d  stloc.2
0x5a6e  ldloca.s 2
0x5a70  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x5a76  callvirt instance string [mscorlib]System.Object::ToString()
0x5a7b  ldstr    asc_E1E0// "']"
0x5a80  call     string [mscorlib]System.String::Concat(string, string, string)
0x5a85  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x5a8a  stloc.1
0x5a8b  ldloc.1
0x5a8c  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5a91  stloc.3
0x5a92  br       loc_5CED
0x5a97  ldloc.3
0x5a98  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5a9d  castclass [System.Xml]System.Xml.XmlNode
0x5aa2  dup
0x5aa3  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5aa8  ldstr    aTargetentityna_0// "TargetEntityName"
0x5aad  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5ab2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5ab7  stloc.s  4
0x5ab9  ldstr    aAttributemapsA// "AttributeMaps/AttributeMap[not(@Unused)"...
0x5abe  ldc.i4.2
0x5abf  stloc.2
0x5ac0  ldloca.s 2
0x5ac2  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x5ac8  callvirt instance string [mscorlib]System.Object::ToString()
0x5acd  ldstr    aPicklistmaps// "']/PicklistMaps"
0x5ad2  call     string [mscorlib]System.String::Concat(string, string, string)
0x5ad7  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x5adc  stloc.s  5
0x5ade  ldloc.s  5
0x5ae0  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5ae5  stloc.s  6
0x5ae7  br       loc_5CBE
0x5aec  ldloc.s  6
0x5aee  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5af3  castclass [System.Xml]System.Xml.XmlNode
0x5af8  dup
0x5af9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x5afe  ldstr    aTargetattribut// "TargetAttributeName"
0x5b03  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5b08  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5b0d  stloc.s  7
0x5b0f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5b14  stloc.s  8
0x5b16  ldstr    aPicklistmap// "PicklistMap"
0x5b1b  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x5b20  stloc.s  9
0x5b22  ldloc.s  9
0x5b24  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5b29  stloc.s  0xB
0x5b2b  br.s     loc_5BAA
0x5b2d  ldloc.s  0xB
0x5b2f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5b34  castclass [System.Xml]System.Xml.XmlNode
0x5b39  stloc.s  0xC
0x5b3b  ldc.i4.3
0x5b3c  stloc.2
0x5b3d  ldloca.s 2
0x5b3f  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x5b45  callvirt instance string [mscorlib]System.Object::ToString()
0x5b4a  ldloc.s  0xC
0x5b4c  ldstr    aProcesscode// "ProcessCode"
0x5b51  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5b56  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5b5b  callvirt instance bool [mscorlib]System.String::Equals(string)
0x5b60  brfalse.s loc_5BAA
0x5b62  ldloc.s  0xC
0x5b64  ldstr    aTargetvaluenam// "TargetValueName"
0x5b69  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5b6e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5b73  stloc.s  0xD
0x5b75  ldloc.s  8
0x5b77  ldloc.s  0xD
0x5b79  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x5b7e  brtrue.s loc_5BAA
0x5b80  ldloc.s  8
0x5b82  ldloc.s  0xC
0x5b84  ldstr    aTargetvaluenam// "TargetValueName"
0x5b89  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5b8e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5b93  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5b98  ldloc.0
0x5b99  ldloc.s  4
0x5b9b  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x5ba0  brtrue.s loc_5BAA
0x5ba2  ldloc.0
0x5ba3  ldloc.s  4
0x5ba5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5baa  ldloc.s  0xB
0x5bac  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5bb1  brtrue   loc_5B2D
0x5bb6  leave.s  loc_5BCD
0x5bb8  ldloc.s  0xB
0x5bba  isinst   [mscorlib]System.IDisposable
0x5bbf  stloc.s  0xE
0x5bc1  ldloc.s  0xE
0x5bc3  brfalse.s loc_5BCC
0x5bc5  ldloc.s  0xE
0x5bc7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5bcc  endfinally
0x5bcd  ldarg.0
0x5bce  ldloc.s  4
0x5bd0  ldloc.s  7
0x5bd2  ldloc.s  8
0x5bd4  call     instance int32[] Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreatePicklistValues(string entityName, string attributeName, class [mscorlib]System.Collections.Generic.List`1<string> optionsToCreate)
0x5bd9  stloc.s  0xA
0x5bdb  ldloc.s  9
0x5bdd  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5be2  stloc.s  0xB
0x5be4  br       loc_5C7C
0x5be9  ldloc.s  0xB
0x5beb  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5bf0  castclass [System.Xml]System.Xml.XmlNode
0x5bf5  stloc.s  0xF
0x5bf7  ldc.i4.3
0x5bf8  stloc.2
0x5bf9  ldloca.s 2
0x5bfb  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x5c01  callvirt instance string [mscorlib]System.Object::ToString()
0x5c06  ldloc.s  0xF
0x5c08  ldstr    aProcesscode// "ProcessCode"
0x5c0d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5c12  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5c17  callvirt instance bool [mscorlib]System.String::Equals(string)
0x5c1c  brfalse.s loc_5C7C
0x5c1e  ldloc.s  8
0x5c20  ldloc.s  0xF
0x5c22  ldstr    aTargetvaluenam// "TargetValueName"
0x5c27  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5c2c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x5c31  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::IndexOf(var<u1>)
0x5c36  stloc.s  0x10
0x5c38  ldloc.s  0xF
0x5c3a  ldstr    aTargetvalue// "TargetValue"
0x5c3f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5c44  ldloc.s  0xA
0x5c46  ldloc.s  0x10
0x5c48  ldelema  [mscorlib]System.Int32
0x5c4d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5c52  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5c57  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x5c5c  ldloc.s  0xF
0x5c5e  ldstr    aProcesscode// "ProcessCode"
0x5c63  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5c68  ldc.i4.2
0x5c69  stloc.2
0x5c6a  ldloca.s 2
0x5c6c  constrained. [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode
0x5c72  callvirt instance string [mscorlib]System.Object::ToString()
0x5c77  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x5c7c  ldloc.s  0xB
0x5c7e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5c83  brtrue   loc_5BE9
0x5c88  leave.s  loc_5C9F
0x5c8a  ldloc.s  0xB
0x5c8c  isinst   [mscorlib]System.IDisposable
0x5c91  stloc.s  0xE
0x5c93  ldloc.s  0xE
0x5c95  brfalse.s loc_5C9E
0x5c97  ldloc.s  0xE
0x5c99  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5c9e  endfinally
0x5c9f  leave.s  loc_5CBE
0x5ca1  stloc.s  0x11
0x5ca3  ldarg.0
0x5ca4  ldarg.1
0x5ca5  ldloc.s  4
0x5ca7  ldloc.s  7
0x5ca9  ldloc.s  0x11
0x5cab  call     instance void Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::UpdateMapXmlForPicklistCustomizationFailure(class [System.Xml]System.Xml.XmlDocument mapDoc, string entityName, string attributeName, class [Microsoft.Crm.Core]Microsoft.Crm.CrmException ex)
0x5cb0  rethrow
0x5cb2  ldloc.s  9
0x5cb4  brfalse.s loc_5CBD
0x5cb6  ldloc.s  9
0x5cb8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5cbd  endfinally
0x5cbe  ldloc.s  6
0x5cc0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5cc5  brtrue   loc_5AEC
0x5cca  leave.s  loc_5CED
0x5ccc  ldloc.s  6
0x5cce  isinst   [mscorlib]System.IDisposable
0x5cd3  stloc.s  0xE
0x5cd5  ldloc.s  0xE
0x5cd7  brfalse.s loc_5CE0
0x5cd9  ldloc.s  0xE
0x5cdb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ce0  endfinally
0x5ce1  ldloc.s  5
0x5ce3  brfalse.s loc_5CEC
0x5ce5  ldloc.s  5
0x5ce7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5cec  endfinally
0x5ced  ldloc.3
0x5cee  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5cf3  brtrue   loc_5A97
0x5cf8  leave.s  loc_5D18
0x5cfa  ldloc.3
0x5cfb  isinst   [mscorlib]System.IDisposable
0x5d00  stloc.s  0xE
0x5d02  ldloc.s  0xE
0x5d04  brfalse.s loc_5D0D
0x5d06  ldloc.s  0xE
0x5d08  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d0d  endfinally
0x5d0e  ldloc.1
0x5d0f  brfalse.s loc_5D17
0x5d11  ldloc.1
0x5d12  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d17  endfinally
0x5d18  ldloc.0
0x5d19  ret
```
