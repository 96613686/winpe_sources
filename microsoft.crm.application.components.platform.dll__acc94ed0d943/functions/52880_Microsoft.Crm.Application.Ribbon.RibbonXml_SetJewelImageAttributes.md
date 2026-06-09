# Microsoft.Crm.Application.Ribbon.RibbonXml::SetJewelImageAttributes

- ea: `0x52880`
- end: `0x52c99`
- name: `Microsoft.Crm.Application.Ribbon.RibbonXml::SetJewelImageAttributes`
- size: `1049`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x52810`

## callees

- `0x39f50`
- `0x52880`

## string_xrefs

- `0x52900`: `ImageLeftSide`
- `0x52913`: `ImageLeftSideHover`
- `0x52926`: `ImageLeftSideDown`
- `0x52939`: `ImageRightSide`
- `0x5294c`: `ImageRightSideHover`
- `0x5295f`: `ImageRightSideDown`
- `0x529c0`: `Image{0}SideTop`
- `0x52a44`: `Image{0}SideTop`
- `0x529ec`: `Image{0}SideHoverTop`
- `0x52a70`: `Image{0}SideHoverTop`
- `0x52a18`: `Image{0}SideDownTop`
- `0x52a9c`: `Image{0}SideDownTop`
- `0x52b0b`: `ImageLeftSideLeft`
- `0x52b23`: `ImageLeftSideHoverLeft`
- `0x52b3b`: `ImageLeftSideDownLeft`
- `0x52b53`: `ImageRightSideLeft`
- `0x52b6b`: `ImageRightSideHoverLeft`
- `0x52b83`: `ImageRightSideDownLeft`
- `0x52bcf`: `ImageSideArrow`
- `0x52c47`: `ImageSideArrow`
- `0x52bf7`: `ImageSideArrowClass`

## pseudocode

```c

```

## disassembly

```asm
0x52880  ldarg.1
0x52881  brtrue.s loc_5288A
0x52883  ldstr    aLeft// "Left"
0x52888  br.s     loc_5288F
0x5288a  ldstr    aRight// "Right"
0x5288f  stloc.0
0x52890  ldarg.1
0x52891  brtrue.s loc_5289A
0x52893  ldstr    aRight// "Right"
0x52898  br.s     loc_5289F
0x5289a  ldstr    aLeft// "Left"
0x5289f  stloc.1
0x528a0  ldarg.0
0x528a1  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XNode [System.Xml.Linq]System.Xml.Linq.XContainer::get_FirstNode()
0x528a6  castclass [System.Xml.Linq]System.Xml.Linq.XElement
0x528ab  stloc.2
0x528ac  ldstr    aImgsImagestrip// "/_imgs/imagestrips/repeat-x-14.png"
0x528b1  ldarg.3
0x528b2  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::Create(string uri, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x528b7  callvirt instance string [mscorlib]System.Object::ToString()
0x528bc  stloc.3
0x528bd  ldloc.2
0x528be  ldc.i4.s 0x1B
0x528c0  newarr   [mscorlib]System.Object
0x528c5  dup
0x528c6  ldc.i4.0
0x528c7  ldstr    aImage// "Image"
0x528cc  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x528d1  ldloc.3
0x528d2  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x528d7  stelem.ref
0x528d8  dup
0x528d9  ldc.i4.1
0x528da  ldstr    aImagehover// "ImageHover"
0x528df  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x528e4  ldloc.3
0x528e5  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x528ea  stelem.ref
0x528eb  dup
0x528ec  ldc.i4.2
0x528ed  ldstr    aImagedown// "ImageDown"
0x528f2  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x528f7  ldloc.3
0x528f8  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x528fd  stelem.ref
0x528fe  dup
0x528ff  ldc.i4.3
0x52900  ldstr    aImageleftside// "ImageLeftSide"
0x52905  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x5290a  ldloc.3
0x5290b  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52910  stelem.ref
0x52911  dup
0x52912  ldc.i4.4
0x52913  ldstr    aImageleftsideh// "ImageLeftSideHover"
0x52918  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x5291d  ldloc.3
0x5291e  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52923  stelem.ref
0x52924  dup
0x52925  ldc.i4.5
0x52926  ldstr    aImageleftsided// "ImageLeftSideDown"
0x5292b  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52930  ldloc.3
0x52931  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52936  stelem.ref
0x52937  dup
0x52938  ldc.i4.6
0x52939  ldstr    aImagerightside// "ImageRightSide"
0x5293e  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52943  ldloc.3
0x52944  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52949  stelem.ref
0x5294a  dup
0x5294b  ldc.i4.7
0x5294c  ldstr    aImagerightside_0// "ImageRightSideHover"
0x52951  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52956  ldloc.3
0x52957  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x5295c  stelem.ref
0x5295d  dup
0x5295e  ldc.i4.8
0x5295f  ldstr    aImagerightside_1// "ImageRightSideDown"
0x52964  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52969  ldloc.3
0x5296a  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x5296f  stelem.ref
0x52970  dup
0x52971  ldc.i4.s 9
0x52973  ldstr    aImagetop// "ImageTop"
0x52978  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x5297d  ldstr    a105// "-105"
0x52982  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52987  stelem.ref
0x52988  dup
0x52989  ldc.i4.s 0xA
0x5298b  ldstr    aImagehovertop// "ImageHoverTop"
0x52990  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52995  ldstr    a27// "-27"
0x5299a  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x5299f  stelem.ref
0x529a0  dup
0x529a1  ldc.i4.s 0xB
0x529a3  ldstr    aImagedowntop// "ImageDownTop"
0x529a8  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x529ad  ldstr    a183// "-183"
0x529b2  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x529b7  stelem.ref
0x529b8  dup
0x529b9  ldc.i4.s 0xC
0x529bb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x529c0  ldstr    aImage0Sidetop// "Image{0}SideTop"
0x529c5  ldc.i4.1
0x529c6  newarr   [mscorlib]System.Object
0x529cb  dup
0x529cc  ldc.i4.0
0x529cd  ldloc.0
0x529ce  stelem.ref
0x529cf  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x529d4  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x529d9  ldstr    a79// "-79"
0x529de  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x529e3  stelem.ref
0x529e4  dup
0x529e5  ldc.i4.s 0xD
0x529e7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x529ec  ldstr    aImage0Sidehove// "Image{0}SideHoverTop"
0x529f1  ldc.i4.1
0x529f2  newarr   [mscorlib]System.Object
0x529f7  dup
0x529f8  ldc.i4.0
0x529f9  ldloc.0
0x529fa  stelem.ref
0x529fb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x52a00  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52a05  ldstr    a1_0// "-1"
0x52a0a  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52a0f  stelem.ref
0x52a10  dup
0x52a11  ldc.i4.s 0xE
0x52a13  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x52a18  ldstr    aImage0Sidedown// "Image{0}SideDownTop"
0x52a1d  ldc.i4.1
0x52a1e  newarr   [mscorlib]System.Object
0x52a23  dup
0x52a24  ldc.i4.0
0x52a25  ldloc.0
0x52a26  stelem.ref
0x52a27  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x52a2c  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52a31  ldstr    a157// "-157"
0x52a36  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52a3b  stelem.ref
0x52a3c  dup
0x52a3d  ldc.i4.s 0xF
0x52a3f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x52a44  ldstr    aImage0Sidetop// "Image{0}SideTop"
0x52a49  ldc.i4.1
0x52a4a  newarr   [mscorlib]System.Object
0x52a4f  dup
0x52a50  ldc.i4.0
0x52a51  ldloc.1
0x52a52  stelem.ref
0x52a53  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x52a58  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52a5d  ldstr    a131// "-131"
0x52a62  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52a67  stelem.ref
0x52a68  dup
0x52a69  ldc.i4.s 0x10
0x52a6b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x52a70  ldstr    aImage0Sidehove// "Image{0}SideHoverTop"
0x52a75  ldc.i4.1
0x52a76  newarr   [mscorlib]System.Object
0x52a7b  dup
0x52a7c  ldc.i4.0
0x52a7d  ldloc.1
0x52a7e  stelem.ref
0x52a7f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x52a84  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52a89  ldstr    a53// "-53"
0x52a8e  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52a93  stelem.ref
0x52a94  dup
0x52a95  ldc.i4.s 0x11
0x52a97  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x52a9c  ldstr    aImage0Sidedown// "Image{0}SideDownTop"
0x52aa1  ldc.i4.1
0x52aa2  newarr   [mscorlib]System.Object
0x52aa7  dup
0x52aa8  ldc.i4.0
0x52aa9  ldloc.1
0x52aaa  stelem.ref
0x52aab  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x52ab0  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52ab5  ldstr    a209// "-209"
0x52aba  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52abf  stelem.ref
0x52ac0  dup
0x52ac1  ldc.i4.s 0x12
0x52ac3  ldstr    aImageleft// "ImageLeft"
0x52ac8  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52acd  ldstr    a0_0// "0"
0x52ad2  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52ad7  stelem.ref
0x52ad8  dup
0x52ad9  ldc.i4.s 0x13
0x52adb  ldstr    aImagehoverleft// "ImageHoverLeft"
0x52ae0  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52ae5  ldstr    a0_0// "0"
0x52aea  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52aef  stelem.ref
0x52af0  dup
0x52af1  ldc.i4.s 0x14
0x52af3  ldstr    aImagedownleft// "ImageDownLeft"
0x52af8  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52afd  ldstr    a0_0// "0"
0x52b02  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52b07  stelem.ref
0x52b08  dup
0x52b09  ldc.i4.s 0x15
0x52b0b  ldstr    aImageleftsidel// "ImageLeftSideLeft"
0x52b10  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52b15  ldstr    a0_0// "0"
0x52b1a  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52b1f  stelem.ref
0x52b20  dup
0x52b21  ldc.i4.s 0x16
0x52b23  ldstr    aImageleftsideh_0// "ImageLeftSideHoverLeft"
0x52b28  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52b2d  ldstr    a0_0// "0"
0x52b32  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52b37  stelem.ref
0x52b38  dup
0x52b39  ldc.i4.s 0x17
0x52b3b  ldstr    aImageleftsided_0// "ImageLeftSideDownLeft"
0x52b40  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52b45  ldstr    a0_0// "0"
0x52b4a  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52b4f  stelem.ref
0x52b50  dup
0x52b51  ldc.i4.s 0x18
0x52b53  ldstr    aImagerightside_2// "ImageRightSideLeft"
0x52b58  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52b5d  ldstr    a0_0// "0"
0x52b62  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52b67  stelem.ref
0x52b68  dup
0x52b69  ldc.i4.s 0x19
0x52b6b  ldstr    aImagerightside_3// "ImageRightSideHoverLeft"
0x52b70  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52b75  ldstr    a0_0// "0"
0x52b7a  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52b7f  stelem.ref
0x52b80  dup
0x52b81  ldc.i4.s 0x1A
0x52b83  ldstr    aImagerightside_4// "ImageRightSideDownLeft"
0x52b88  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52b8d  ldstr    a0_0// "0"
0x52b92  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52b97  stelem.ref
0x52b98  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XContainer::Add(object[])
0x52b9d  ldarg.2
0x52b9e  brfalse  loc_52C3E
0x52ba3  ldarg.1
0x52ba4  brtrue.s loc_52BAD
0x52ba6  ldstr    aRight_0// "right"
0x52bab  br.s     loc_52BB2
0x52bad  ldstr    aLeft_0// "left"
0x52bb2  stloc.s  4
0x52bb4  ldstr    aImgsImagestrip_0// "/_imgs/imagestrips/transparent_spacer.g"...
0x52bb9  ldarg.3
0x52bba  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::Create(string uri, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x52bbf  callvirt instance string [mscorlib]System.Object::ToString()
0x52bc4  stloc.s  5
0x52bc6  ldloc.2
0x52bc7  ldc.i4.4
0x52bc8  newarr   [mscorlib]System.Object
0x52bcd  dup
0x52bce  ldc.i4.0
0x52bcf  ldstr    aImagesidearrow// "ImageSideArrow"
0x52bd4  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52bd9  ldloc.s  5
0x52bdb  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52be0  stelem.ref
0x52be1  dup
0x52be2  ldc.i4.1
0x52be3  ldstr    aImagedownarrow// "ImageDownArrow"
0x52be8  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52bed  ldloc.s  5
0x52bef  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x52bf4  stelem.ref
0x52bf5  dup
0x52bf6  ldc.i4.2
0x52bf7  ldstr    aImagesidearrow_0// "ImageSideArrowClass"
0x52bfc  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x52c01  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x52c06  ldstr    aMsCrmImagestri// "ms-crm-ImageStrip-arrow_{0}"
0x52c0b  ldc.i4.1
0x52c0c  newarr   [mscorlib]System.Object
  ... truncated ...
```
