# Microsoft.Crm.Application.Components.UI.ImageStrip::ProcessImageDefinitions

- ea: `0x1a150`
- end: `0x1a2cd`
- name: `Microsoft.Crm.Application.Components.UI.ImageStrip::ProcessImageDefinitions`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1a040`

## callees

- `0x1a150`
- `0x1a2f0`

## string_xrefs

- `0x1a1b7`: `An Image can be present in the definition file only once. Image {0} occurs in more than once, please remove the duplicate OR change the image id and url.`
- `0x1a20c`: `Replace`

## pseudocode

```c

```

## disassembly

```asm
0x1a150  ldarg.1
0x1a151  ldstr    aImagestrip// "//ImageStrip"
0x1a156  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1a15b  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1a160  stloc.0
0x1a161  br       loc_1A2AB
0x1a166  ldloc.0
0x1a167  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1a16c  castclass [System.Xml]System.Xml.XmlNode
0x1a171  ldstr    aImage// "Image"
0x1a176  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1a17b  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1a180  stloc.1
0x1a181  br       loc_1A28A
0x1a186  ldloc.1
0x1a187  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1a18c  castclass [System.Xml]System.Xml.XmlNode
0x1a191  stloc.2
0x1a192  ldloc.2
0x1a193  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1a198  ldstr    aUrl// "url"
0x1a19d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x1a1a2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1a1a7  stloc.3
0x1a1a8  ldarg.0
0x1a1a9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo> Microsoft.Crm.Application.Components.UI.ImageStrip::_imageDefinitions
0x1a1ae  ldloc.3
0x1a1af  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo>::ContainsKey(var<u1>)
0x1a1b4  ldc.i4.0
0x1a1b5  ceq
0x1a1b7  ldstr    aAnImageCanBePr// "An Image can be present in the definiti"...
0x1a1bc  ldc.i4.1
0x1a1bd  newarr   [mscorlib]System.Object
0x1a1c2  dup
0x1a1c3  ldc.i4.0
0x1a1c4  ldloc.3
0x1a1c5  stelem.ref
0x1a1c6  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string, object[])
0x1a1cb  ldloc.2
0x1a1cc  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1a1d1  ldstr    aId// "id"
0x1a1d6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x1a1db  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1a1e0  stloc.s  4
0x1a1e2  ldnull
0x1a1e3  stloc.s  5
0x1a1e5  ldloc.2
0x1a1e6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1a1eb  ldstr    aFlipmode// "flipmode"
0x1a1f0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x1a1f5  brfalse.s loc_1A256
0x1a1f7  ldloc.2
0x1a1f8  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1a1fd  ldstr    aFlipmode// "flipmode"
0x1a202  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x1a207  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1a20c  ldstr    aReplace// "Replace"
0x1a211  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1a216  brfalse.s loc_1A256
0x1a218  ldloc.2
0x1a219  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1a21e  ldstr    aRtlurl// "Rtlurl"
0x1a223  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x1a228  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1a22d  stloc.3
0x1a22e  ldloc.s  4
0x1a230  ldloc.3
0x1a231  ldstr    aMsCrmImagestri// "ms-crm-ImageStripRtl-"
0x1a236  ldloc.s  4
0x1a238  ldstr    aAZaZ09// "[^A-Za-z0-9_\\-]"
0x1a23d  ldstr    asc_535CC// "_"
0x1a242  call     string [System]System.Text.RegularExpressions.Regex::Replace(string, string, string)
0x1a247  call     string [mscorlib]System.String::Concat(string, string)
0x1a24c  ldc.i4.1
0x1a24d  newobj   instance void Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::.ctor(string id, string url, string cssClass, bool isPartOfImageStrip)
0x1a252  stloc.s  5
0x1a254  br.s     loc_1A27C
0x1a256  ldloc.s  4
0x1a258  ldloc.3
0x1a259  ldstr    aMsCrmImagestri_0// "ms-crm-ImageStrip-"
0x1a25e  ldloc.s  4
0x1a260  ldstr    aAZaZ09// "[^A-Za-z0-9_\\-]"
0x1a265  ldstr    asc_535CC// "_"
0x1a26a  call     string [System]System.Text.RegularExpressions.Regex::Replace(string, string, string)
0x1a26f  call     string [mscorlib]System.String::Concat(string, string)
0x1a274  ldc.i4.1
0x1a275  newobj   instance void Microsoft.Crm.Application.Components.UI.ImageStripImageInfo::.ctor(string id, string url, string cssClass, bool isPartOfImageStrip)
0x1a27a  stloc.s  5
0x1a27c  ldarg.0
0x1a27d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo> Microsoft.Crm.Application.Components.UI.ImageStrip::_imageDefinitions
0x1a282  ldloc.3
0x1a283  ldloc.s  5
0x1a285  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Application.Components.UI.ImageStripImageInfo>::Add(var<u1>, !!T0)
0x1a28a  ldloc.1
0x1a28b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a290  brtrue   loc_1A186
0x1a295  leave.s  loc_1A2AB
0x1a297  ldloc.1
0x1a298  isinst   [mscorlib]System.IDisposable
0x1a29d  stloc.s  6
0x1a29f  ldloc.s  6
0x1a2a1  brfalse.s loc_1A2AA
0x1a2a3  ldloc.s  6
0x1a2a5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a2aa  endfinally
0x1a2ab  ldloc.0
0x1a2ac  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a2b1  brtrue   loc_1A166
0x1a2b6  leave.s  loc_1A2CC
0x1a2b8  ldloc.0
0x1a2b9  isinst   [mscorlib]System.IDisposable
0x1a2be  stloc.s  6
0x1a2c0  ldloc.s  6
0x1a2c2  brfalse.s loc_1A2CB
0x1a2c4  ldloc.s  6
0x1a2c6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a2cb  endfinally
0x1a2cc  ret
```
