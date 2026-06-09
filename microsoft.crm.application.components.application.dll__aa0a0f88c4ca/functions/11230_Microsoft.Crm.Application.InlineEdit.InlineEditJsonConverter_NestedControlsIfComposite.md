# Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::NestedControlsIfComposite

- ea: `0x11230`
- end: `0x113b7`
- name: `Microsoft.Crm.Application.InlineEdit.InlineEditJsonConverter::NestedControlsIfComposite`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10fc0`

## callees

- `0x11230`

## string_xrefs

- `0x11339`: `composite`
- `0x1126a`: `_compositionLinkControl_`
- `0x11329`: `_compositionLinkControl_`
- `0x112fd`: `billto_composite`
- `0x11314`: `shipto_composite`

## pseudocode

```c

```

## disassembly

```asm
0x11230  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x11235  stloc.0
0x11236  ldarg.0
0x11237  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x1123c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x11241  ldstr    aFullname// "fullname"
0x11246  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1124b  brtrue.s loc_11264
0x1124d  ldarg.0
0x1124e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x11253  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x11258  ldstr    aYomifullname// "yomifullname"
0x1125d  callvirt instance bool [mscorlib]System.String::Equals(string)
0x11262  brfalse.s loc_112DA
0x11264  ldarg.0
0x11265  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_ID()
0x1126a  ldstr    aCompositionlin// "_compositionLinkControl_"
0x1126f  call     string [mscorlib]System.String::Concat(string, string)
0x11274  stloc.1
0x11275  ldarg.0
0x11276  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x1127b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x11280  ldstr    aYomifullname// "yomifullname"
0x11285  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1128a  brfalse.s loc_11298
0x1128c  ldloc.1
0x1128d  ldstr    aYomi// "yomi"
0x11292  call     string [mscorlib]System.String::Concat(string, string)
0x11297  stloc.1
0x11298  ldc.i4.3
0x11299  newarr   [mscorlib]System.String
0x1129e  dup
0x1129f  ldc.i4.0
0x112a0  ldstr    aFirstname// "firstname"
0x112a5  stelem.ref
0x112a6  dup
0x112a7  ldc.i4.1
0x112a8  ldstr    aMiddlename// "middlename"
0x112ad  stelem.ref
0x112ae  dup
0x112af  ldc.i4.2
0x112b0  ldstr    aLastname// "lastname"
0x112b5  stelem.ref
0x112b6  stloc.2
0x112b7  ldc.i4.0
0x112b8  stloc.3
0x112b9  br.s     loc_112CF
0x112bb  ldloc.0
0x112bc  ldloc.1
0x112bd  ldloc.2
0x112be  ldloc.3
0x112bf  ldelem.ref
0x112c0  call     string [mscorlib]System.String::Concat(string, string)
0x112c5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x112ca  pop
0x112cb  ldloc.3
0x112cc  ldc.i4.1
0x112cd  add
0x112ce  stloc.3
0x112cf  ldloc.3
0x112d0  ldloc.2
0x112d1  ldlen
0x112d2  conv.i4
0x112d3  blt.s    loc_112BB
0x112d5  br       loc_113B5
0x112da  ldarg.0
0x112db  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x112e0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x112e5  ldstr    aAddress// "address"
0x112ea  ldc.i4.4
0x112eb  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x112f0  brtrue.s loc_11323
0x112f2  ldarg.0
0x112f3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x112f8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x112fd  ldstr    aBilltoComposit// "billto_composite"
0x11302  callvirt instance bool [mscorlib]System.String::Equals(string)
0x11307  brtrue.s loc_11323
0x11309  ldarg.0
0x1130a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x1130f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x11314  ldstr    aShiptoComposit// "shipto_composite"
0x11319  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1131e  brfalse  loc_113B5
0x11323  ldarg.0
0x11324  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_ID()
0x11329  ldstr    aCompositionlin// "_compositionLinkControl_"
0x1132e  ldarg.0
0x1132f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x11334  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x11339  ldstr    aComposite// "composite"
0x1133e  ldstr    asc_F537C// ""
0x11343  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11348  call     string [mscorlib]System.String::Concat(string, string, string)
0x1134d  stloc.s  4
0x1134f  ldc.i4.7
0x11350  newarr   [mscorlib]System.String
0x11355  dup
0x11356  ldc.i4.0
0x11357  ldstr    aLine1// "line1"
0x1135c  stelem.ref
0x1135d  dup
0x1135e  ldc.i4.1
0x1135f  ldstr    aLine2// "line2"
0x11364  stelem.ref
0x11365  dup
0x11366  ldc.i4.2
0x11367  ldstr    aLine3// "line3"
0x1136c  stelem.ref
0x1136d  dup
0x1136e  ldc.i4.3
0x1136f  ldstr    aCity// "city"
0x11374  stelem.ref
0x11375  dup
0x11376  ldc.i4.4
0x11377  ldstr    aStateorprovinc// "stateorprovince"
0x1137c  stelem.ref
0x1137d  dup
0x1137e  ldc.i4.5
0x1137f  ldstr    aPostalcode// "postalcode"
0x11384  stelem.ref
0x11385  dup
0x11386  ldc.i4.6
0x11387  ldstr    aCountry// "country"
0x1138c  stelem.ref
0x1138d  stloc.s  5
0x1138f  ldc.i4.0
0x11390  stloc.s  6
0x11392  br.s     loc_113AD
0x11394  ldloc.0
0x11395  ldloc.s  4
0x11397  ldloc.s  5
0x11399  ldloc.s  6
0x1139b  ldelem.ref
0x1139c  call     string [mscorlib]System.String::Concat(string, string)
0x113a1  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x113a6  pop
0x113a7  ldloc.s  6
0x113a9  ldc.i4.1
0x113aa  add
0x113ab  stloc.s  6
0x113ad  ldloc.s  6
0x113af  ldloc.s  5
0x113b1  ldlen
0x113b2  conv.i4
0x113b3  blt.s    loc_11394
0x113b5  ldloc.0
0x113b6  ret
```
