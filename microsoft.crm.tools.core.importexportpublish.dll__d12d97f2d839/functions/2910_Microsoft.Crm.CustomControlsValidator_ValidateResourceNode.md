# Microsoft.Crm.CustomControlsValidator::ValidateResourceNode

- ea: `0x2910`
- end: `0x2e06`
- name: `Microsoft.Crm.CustomControlsValidator::ValidateResourceNode`
- size: `1270`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2c0`

## callees

- `0x2910`
- `0x3930`
- `0x3a00`
- `0x3c00`

## string_xrefs

- `0x297d`: `/manifest/control[@namespace="`
- `0x2bf4`: `/manifest/control[@namespace="`
- `0x2c49`: `/manifest/control[@namespace="`
- `0x2c9e`: `/manifest/control[@namespace="`
- `0x2cfb`: `/manifest/control[@namespace="`

## pseudocode

```c

```

## disassembly

```asm
0x2910  ldarg.0
0x2911  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.CustomControlsValidator::ReadManifest()
0x2916  stloc.0
0x2917  ldarg.0
0x2918  ldloc.0
0x2919  ldloca.s 1
0x291b  ldloca.s 2
0x291d  call     instance void Microsoft.Crm.CustomControlsValidator::ParseToGetControlNames(class [System.Xml]System.Xml.XmlDocument doc, [out] class [mscorlib]System.Collections.ObjectModel.Collection`1<string>& controlNames, [out] bool& success)
0x2922  ldloc.1
0x2923  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::GetEnumerator()
0x2928  stloc.3
0x2929  br       loc_2DEA
0x292e  ldloc.3
0x292f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x2934  stloc.s  4
0x2936  ldloc.s  4
0x2938  ldc.i4.1
0x2939  newarr   [mscorlib]System.Char
0x293e  dup
0x293f  ldc.i4.0
0x2940  ldc.i4.s 0x2F
0x2942  stelem.i2
0x2943  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x2948  ldc.i4.0
0x2949  callvirt instance object [mscorlib]System.Array::GetValue(int32)
0x294e  callvirt instance string [mscorlib]System.Object::ToString()
0x2953  stloc.s  5
0x2955  ldloc.s  4
0x2957  ldc.i4.1
0x2958  newarr   [mscorlib]System.Char
0x295d  dup
0x295e  ldc.i4.0
0x295f  ldc.i4.s 0x2F
0x2961  stelem.i2
0x2962  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x2967  ldc.i4.1
0x2968  callvirt instance object [mscorlib]System.Array::GetValue(int32)
0x296d  callvirt instance string [mscorlib]System.Object::ToString()
0x2972  stloc.s  6
0x2974  ldloc.0
0x2975  ldc.i4.5
0x2976  newarr   [mscorlib]System.String
0x297b  dup
0x297c  ldc.i4.0
0x297d  ldstr    aManifestContro_17// "/manifest/control[@namespace=\""
0x2982  stelem.ref
0x2983  dup
0x2984  ldc.i4.1
0x2985  ldloc.s  5
0x2987  stelem.ref
0x2988  dup
0x2989  ldc.i4.2
0x298a  ldstr    aAndConstructor_0// "\"and @constructor=\""
0x298f  stelem.ref
0x2990  dup
0x2991  ldc.i4.3
0x2992  ldloc.s  6
0x2994  stelem.ref
0x2995  dup
0x2996  ldc.i4.4
0x2997  ldstr    aResources// "\"]/resources"
0x299c  stelem.ref
0x299d  call     string [mscorlib]System.String::Concat(string[])
0x29a2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x29a7  stloc.s  7
0x29a9  ldloc.s  7
0x29ab  ldstr    aLibrary// "/library"
0x29b0  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x29b5  stloc.s  0xB
0x29b7  ldloc.s  0xB
0x29b9  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x29be  stloc.s  0xC
0x29c0  br       loc_2BBC
0x29c5  ldloc.s  0xC
0x29c7  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x29cc  castclass [System.Xml]System.Xml.XmlNode
0x29d1  stloc.s  0xD
0x29d3  ldloc.s  0xD
0x29d5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x29da  ldstr    aName// "name"
0x29df  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x29e4  brfalse.s loc_2A03
0x29e6  ldloc.s  0xD
0x29e8  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x29ed  ldstr    aName// "name"
0x29f2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x29f7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x29fc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a01  brfalse.s loc_2A0B
0x2a03  ldc.i4.0
0x2a04  stloc.s  0xE
0x2a06  leave    loc_2E03
0x2a0b  ldloc.s  0xD
0x2a0d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2a12  ldstr    aVersion// "version"
0x2a17  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2a1c  brfalse.s loc_2A3B
0x2a1e  ldloc.s  0xD
0x2a20  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2a25  ldstr    aVersion// "version"
0x2a2a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2a2f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2a34  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a39  brfalse.s loc_2A43
0x2a3b  ldc.i4.0
0x2a3c  stloc.s  0xE
0x2a3e  leave    loc_2E03
0x2a43  ldloc.s  0xD
0x2a45  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2a4a  ldstr    aOrder// "order"
0x2a4f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2a54  brfalse.s loc_2A73
0x2a56  ldloc.s  0xD
0x2a58  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2a5d  ldstr    aOrder// "order"
0x2a62  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2a67  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2a6c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a71  brfalse.s loc_2A7B
0x2a73  ldc.i4.0
0x2a74  stloc.s  0xE
0x2a76  leave    loc_2E03
0x2a7b  ldloc.s  7
0x2a7d  ldstr    aLibraryName// "/library[@name=\""
0x2a82  ldloc.s  0xD
0x2a84  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2a89  ldstr    aName// "name"
0x2a8e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2a93  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2a98  ldstr    aPackagedLibrar// "\"]/packaged_library"
0x2a9d  call     string [mscorlib]System.String::Concat(string, string, string)
0x2aa2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x2aa7  stloc.s  0xF
0x2aa9  ldloc.s  0xF
0x2aab  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x2ab0  stloc.s  0x10
0x2ab2  br       loc_2B8D
0x2ab7  ldloc.s  0x10
0x2ab9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2abe  castclass [System.Xml]System.Xml.XmlNode
0x2ac3  stloc.s  0x11
0x2ac5  ldloc.s  0x11
0x2ac7  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2acc  ldstr    aPath// "path"
0x2ad1  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2ad6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2adb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2ae0  brfalse.s loc_2AEA
0x2ae2  ldc.i4.0
0x2ae3  stloc.s  0xE
0x2ae5  leave    loc_2E03
0x2aea  ldloc.s  0x11
0x2aec  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2af1  ldstr    aPath// "path"
0x2af6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2afb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2b00  ldc.i4.1
0x2b01  newarr   [mscorlib]System.Char
0x2b06  dup
0x2b07  ldc.i4.0
0x2b08  ldc.i4.s 0x2E
0x2b0a  stelem.i2
0x2b0b  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x2b10  ldc.i4.1
0x2b11  ldelem.ref
0x2b12  ldstr    aJs// "js"
0x2b17  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2b1c  brfalse.s loc_2B26
0x2b1e  ldc.i4.0
0x2b1f  stloc.s  0xE
0x2b21  leave    loc_2E03
0x2b26  ldloc.s  0x11
0x2b28  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2b2d  ldstr    aVersion// "version"
0x2b32  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2b37  brfalse.s loc_2B56
0x2b39  ldloc.s  0x11
0x2b3b  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2b40  ldstr    aVersion// "version"
0x2b45  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2b4a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2b4f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2b54  brfalse.s loc_2B5E
0x2b56  ldc.i4.0
0x2b57  stloc.s  0xE
0x2b59  leave    loc_2E03
0x2b5e  ldloc.s  0x11
0x2b60  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x2b65  ldstr    aVersion// "version"
0x2b6a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2b6f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2b74  ldstr    a09092// "^[0-9]*([\\.][0-9]*){2}$"
0x2b79  call     class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string, string)
0x2b7e  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x2b83  brtrue.s loc_2B8D
0x2b85  ldc.i4.0
0x2b86  stloc.s  0xE
0x2b88  leave    loc_2E03
0x2b8d  ldloc.s  0x10
0x2b8f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2b94  brtrue   loc_2AB7
0x2b99  leave.s  loc_2BBC
0x2b9b  ldloc.s  0x10
0x2b9d  isinst   [mscorlib]System.IDisposable
0x2ba2  stloc.s  0x12
0x2ba4  ldloc.s  0x12
0x2ba6  brfalse.s loc_2BAF
0x2ba8  ldloc.s  0x12
0x2baa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2baf  endfinally
0x2bb0  ldloc.s  0xF
0x2bb2  brfalse.s loc_2BBB
0x2bb4  ldloc.s  0xF
0x2bb6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2bbb  endfinally
0x2bbc  ldloc.s  0xC
0x2bbe  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2bc3  brtrue   loc_29C5
0x2bc8  leave.s  loc_2BEB
0x2bca  ldloc.s  0xC
0x2bcc  isinst   [mscorlib]System.IDisposable
0x2bd1  stloc.s  0x12
0x2bd3  ldloc.s  0x12
0x2bd5  brfalse.s loc_2BDE
0x2bd7  ldloc.s  0x12
0x2bd9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2bde  endfinally
0x2bdf  ldloc.s  0xB
0x2be1  brfalse.s loc_2BEA
0x2be3  ldloc.s  0xB
0x2be5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2bea  endfinally
0x2beb  ldloc.0
0x2bec  ldc.i4.5
0x2bed  newarr   [mscorlib]System.String
0x2bf2  dup
0x2bf3  ldc.i4.0
0x2bf4  ldstr    aManifestContro_17// "/manifest/control[@namespace=\""
0x2bf9  stelem.ref
0x2bfa  dup
0x2bfb  ldc.i4.1
0x2bfc  ldloc.s  5
0x2bfe  stelem.ref
0x2bff  dup
0x2c00  ldc.i4.2
0x2c01  ldstr    aAndConstructor_0// "\"and @constructor=\""
0x2c06  stelem.ref
0x2c07  dup
0x2c08  ldc.i4.3
0x2c09  ldloc.s  6
0x2c0b  stelem.ref
0x2c0c  dup
0x2c0d  ldc.i4.4
0x2c0e  ldstr    aResourcesCode// "\"]/resources/code"
0x2c13  stelem.ref
0x2c14  call     string [mscorlib]System.String::Concat(string[])
0x2c19  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2c1e  stloc.s  8
0x2c20  ldarg.0
0x2c21  ldloc.s  8
0x2c23  ldc.i4.1
0x2c24  newarr   [mscorlib]System.String
0x2c29  dup
0x2c2a  ldc.i4.0
0x2c2b  ldstr    aJs// "js"
0x2c30  stelem.ref
0x2c31  call     instance bool Microsoft.Crm.CustomControlsValidator::ParseResourcePath(class [System.Xml]System.Xml.XmlNode resourceChild, string[] resourceType)
0x2c36  brtrue.s loc_2C40
0x2c38  ldc.i4.0
0x2c39  stloc.s  0xE
0x2c3b  leave    loc_2E03
0x2c40  ldloc.0
0x2c41  ldc.i4.5
0x2c42  newarr   [mscorlib]System.String
0x2c47  dup
0x2c48  ldc.i4.0
0x2c49  ldstr    aManifestContro_17// "/manifest/control[@namespace=\""
0x2c4e  stelem.ref
0x2c4f  dup
0x2c50  ldc.i4.1
0x2c51  ldloc.s  5
0x2c53  stelem.ref
0x2c54  dup
0x2c55  ldc.i4.2
0x2c56  ldstr    aAndConstructor_0// "\"and @constructor=\""
0x2c5b  stelem.ref
0x2c5c  dup
0x2c5d  ldc.i4.3
0x2c5e  ldloc.s  6
0x2c60  stelem.ref
0x2c61  dup
0x2c62  ldc.i4.4
0x2c63  ldstr    aResourcesCss// "\"]/resources/css"
0x2c68  stelem.ref
0x2c69  call     string [mscorlib]System.String::Concat(string[])
0x2c6e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2c73  stloc.s  9
0x2c75  ldarg.0
0x2c76  ldloc.s  9
0x2c78  ldc.i4.1
  ... truncated ...
```
