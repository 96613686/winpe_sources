# Microsoft.Crm.Metadata.LocalizedLabelDescription::FillPropertiesFromXml_1

- ea: `0x38110`
- end: `0x38642`
- name: `Microsoft.Crm.Metadata.LocalizedLabelDescription::FillPropertiesFromXml_1`
- size: `1330`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x380f0`
- `0x38100`

## callees

- `0xbbf0`
- `0x38110`
- `0x38650`
- `0x38770`
- `0x387d0`
- `0x38820`
- `0x38870`
- `0x38900`
- `0x389f0`
- `0x38a10`
- `0x38a30`
- `0x38a50`
- `0x38a70`
- `0x38a90`
- `0xa94d0`

## string_xrefs

- `0x38319`: `Invalid XML from which to create a label description`
- `0x38577`: `Invalid XML from which to create a label description`
- `0x38599`: `LocalizedLabel XML requires the LocalizedLabel id`

## pseudocode

```c

```

## disassembly

```asm
0x38110  ldarg.1
0x38111  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x38116  stloc.0
0x38117  ldloc.0
0x38118  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x3811d  stloc.1
0x3811e  ldloc.1
0x3811f  ldc.i4   0xB888EEF1
0x38124  bgt.un.s loc_38161
0x38126  ldloc.1
0x38127  ldc.i4   0x4FD51A36
0x3812c  bgt.un.s loc_38146
0x3812e  ldloc.1
0x3812f  ldc.i4   0x3F67CBC4
0x38134  beq      loc_38214
0x38139  ldloc.1
0x3813a  ldc.i4   0x4FD51A36
0x3813f  beq.s    loc_381AB
0x38141  br       loc_38577
0x38146  ldloc.1
0x38147  ldc.i4   0x66DE7A09
0x3814c  beq      loc_381EA
0x38151  ldloc.1
0x38152  ldc.i4   0xB888EEF1
0x38157  beq      loc_38229
0x3815c  br       loc_38577
0x38161  ldloc.1
0x38162  ldc.i4   0xE5B43CF8
0x38167  bgt.un.s loc_38181
0x38169  ldloc.1
0x3816a  ldc.i4   0xCDDC0281
0x3816f  beq.s    loc_381D5
0x38171  ldloc.1
0x38172  ldc.i4   0xE5B43CF8
0x38177  beq      loc_381FF
0x3817c  br       loc_38577
0x38181  ldloc.1
0x38182  ldc.i4   0xF69717FD
0x38187  beq.s    loc_38196
0x38189  ldloc.1
0x3818a  ldc.i4   0xF6CEECB1
0x3818f  beq.s    loc_381C0
0x38191  br       loc_38577
0x38196  ldloc.0
0x38197  ldstr    aLabel_0// "label"
0x3819c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x381a1  brtrue   loc_3823E
0x381a6  br       loc_38577
0x381ab  ldloc.0
0x381ac  ldstr    aDisplayname// "displayname"
0x381b1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x381b6  brtrue   loc_38263
0x381bb  br       loc_38577
0x381c0  ldloc.0
0x381c1  ldstr    aLocalizedname// "LocalizedName"
0x381c6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x381cb  brtrue   loc_38324
0x381d0  br       loc_38577
0x381d5  ldloc.0
0x381d6  ldstr    aLocalizedcolle// "LocalizedCollectionName"
0x381db  call     bool [mscorlib]System.String::op_Equality(string, string)
0x381e0  brtrue   loc_3834A
0x381e5  br       loc_38577
0x381ea  ldloc.0
0x381eb  ldstr    aDescription_0// "Description"
0x381f0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x381f5  brtrue   loc_38370
0x381fa  br       loc_38577
0x381ff  ldloc.0
0x38200  ldstr    aColor// "Color"
0x38205  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3820a  brtrue   loc_384C8
0x3820f  br       loc_38577
0x38214  ldloc.0
0x38215  ldstr    aCustomlabel// "CustomLabel"
0x3821a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3821f  brtrue   loc_384ED
0x38224  br       loc_38577
0x38229  ldloc.0
0x3822a  ldstr    aNonmetadatalab// "NonMetadataLabel"
0x3822f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x38234  brtrue   loc_38510
0x38239  br       loc_38577
0x3823e  ldarg.0
0x3823f  ldstr    aDisplayname_0// "DisplayName"
0x38244  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectColumnName(string value)
0x38249  ldarg.0
0x3824a  ldc.i4.2
0x3824b  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_LabelType(int32 value)
0x38250  ldarg.0
0x38251  ldarg.0
0x38252  ldarg.1
0x38253  ldarg.2
0x38254  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.LocalizedLabelDescription::GetObjectIdForAttributePicklistValue(class [System.Xml]System.Xml.XmlNode node, bool throwIfIdsMissing)
0x38259  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectId(valuetype [mscorlib]System.Guid value)
0x3825e  br       loc_38582
0x38263  ldarg.0
0x38264  ldstr    aDisplayname_0// "DisplayName"
0x38269  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectColumnName(string value)
0x3826e  ldarg.1
0x3826f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x38274  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x38279  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x3827e  ldstr    aAttribute_0// "attribute"
0x38283  call     bool [mscorlib]System.String::op_Equality(string, string)
0x38288  brfalse.s loc_382A5
0x3828a  ldarg.0
0x3828b  ldc.i4.1
0x3828c  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_LabelType(int32 value)
0x38291  ldarg.0
0x38292  ldarg.0
0x38293  ldarg.1
0x38294  ldarg.2
0x38295  ldarg.3
0x38296  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.LocalizedLabelDescription::GetObjectIdForAttribute(class [System.Xml]System.Xml.XmlNode node, bool throwIfIdsMissing, bool fetchMissingIdsFromCache)
0x3829b  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectId(valuetype [mscorlib]System.Guid value)
0x382a0  br       loc_38582
0x382a5  ldarg.1
0x382a6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x382ab  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x382b0  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x382b5  ldstr    aOptionset// "optionset"
0x382ba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x382bf  brfalse.s loc_382DC
0x382c1  ldarg.0
0x382c2  ldc.i4.s 0xA
0x382c4  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_LabelType(int32 value)
0x382c9  ldarg.0
0x382ca  ldarg.0
0x382cb  ldarg.1
0x382cc  ldarg.2
0x382cd  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.LocalizedLabelDescription::GetObjectIdForOptionSet(class [System.Xml]System.Xml.XmlNode node, bool throwIfIdsMissing)
0x382d2  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectId(valuetype [mscorlib]System.Guid value)
0x382d7  br       loc_38582
0x382dc  ldarg.1
0x382dd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x382e2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x382e7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x382ec  ldstr    aManagedpropert// "managedproperty"
0x382f1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x382f6  brfalse.s loc_38313
0x382f8  ldarg.0
0x382f9  ldc.i4.s 0x11
0x382fb  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_LabelType(int32 value)
0x38300  ldarg.0
0x38301  ldarg.0
0x38302  ldarg.1
0x38303  ldarg.2
0x38304  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.LocalizedLabelDescription::GetObjectIdForManagedProperty(class [System.Xml]System.Xml.XmlNode node, bool throwIfIdsMissing)
0x38309  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectId(valuetype [mscorlib]System.Guid value)
0x3830e  br       loc_38582
0x38313  ldarg.2
0x38314  brfalse  loc_38582
0x38319  ldstr    aInvalidXmlFrom// "Invalid XML from which to create a labe"...
0x3831e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x38323  throw
0x38324  ldarg.0
0x38325  ldstr    aLocalizedname// "LocalizedName"
0x3832a  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectColumnName(string value)
0x3832f  ldarg.0
0x38330  ldc.i4.0
0x38331  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_LabelType(int32 value)
0x38336  ldarg.0
0x38337  ldarg.0
0x38338  ldarg.1
0x38339  ldarg.2
0x3833a  ldarg.3
0x3833b  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.LocalizedLabelDescription::GetObjectIdForEntity(class [System.Xml]System.Xml.XmlNode node, bool throwIfIdsMissing, bool fetchMissingIdsFromCache)
0x38340  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectId(valuetype [mscorlib]System.Guid value)
0x38345  br       loc_38582
0x3834a  ldarg.0
0x3834b  ldstr    aLocalizedcolle// "LocalizedCollectionName"
0x38350  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectColumnName(string value)
0x38355  ldarg.0
0x38356  ldc.i4.0
0x38357  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_LabelType(int32 value)
0x3835c  ldarg.0
0x3835d  ldarg.0
0x3835e  ldarg.1
0x3835f  ldarg.2
0x38360  ldarg.3
0x38361  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.LocalizedLabelDescription::GetObjectIdForEntity(class [System.Xml]System.Xml.XmlNode node, bool throwIfIdsMissing, bool fetchMissingIdsFromCache)
0x38366  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectId(valuetype [mscorlib]System.Guid value)
0x3836b  br       loc_38582
0x38370  ldarg.0
0x38371  ldstr    aDescription_0// "Description"
0x38376  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectColumnName(string value)
0x3837b  ldarg.1
0x3837c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x38381  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x38386  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x3838b  ldstr    aAttribute_0// "attribute"
0x38390  call     bool [mscorlib]System.String::op_Equality(string, string)
0x38395  brfalse.s loc_383B2
0x38397  ldarg.0
0x38398  ldc.i4.1
0x38399  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_LabelType(int32 value)
0x3839e  ldarg.0
0x3839f  ldarg.0
0x383a0  ldarg.1
0x383a1  ldarg.2
0x383a2  ldarg.3
0x383a3  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.LocalizedLabelDescription::GetObjectIdForAttribute(class [System.Xml]System.Xml.XmlNode node, bool throwIfIdsMissing, bool fetchMissingIdsFromCache)
0x383a8  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectId(valuetype [mscorlib]System.Guid value)
0x383ad  br       loc_38582
0x383b2  ldarg.1
0x383b3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x383b8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x383bd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x383c2  ldstr    aEntity// "entity"
0x383c7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x383cc  brfalse.s loc_383E9
0x383ce  ldarg.0
0x383cf  ldc.i4.0
0x383d0  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_LabelType(int32 value)
0x383d5  ldarg.0
0x383d6  ldarg.0
0x383d7  ldarg.1
0x383d8  ldarg.2
0x383d9  ldarg.3
0x383da  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.LocalizedLabelDescription::GetObjectIdForEntity(class [System.Xml]System.Xml.XmlNode node, bool throwIfIdsMissing, bool fetchMissingIdsFromCache)
0x383df  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectId(valuetype [mscorlib]System.Guid value)
0x383e4  br       loc_38582
0x383e9  ldarg.1
0x383ea  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x383ef  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x383f4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x383f9  ldstr    aOptionset// "optionset"
0x383fe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x38403  brfalse.s loc_38420
0x38405  ldarg.0
0x38406  ldc.i4.s 0xA
0x38408  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_LabelType(int32 value)
0x3840d  ldarg.0
0x3840e  ldarg.0
0x3840f  ldarg.1
0x38410  ldarg.2
0x38411  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.LocalizedLabelDescription::GetObjectIdForOptionSet(class [System.Xml]System.Xml.XmlNode node, bool throwIfIdsMissing)
0x38416  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectId(valuetype [mscorlib]System.Guid value)
0x3841b  br       loc_38582
0x38420  ldarg.1
0x38421  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x38426  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x3842b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x38430  ldstr    aManagedpropert// "managedproperty"
0x38435  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3843a  brfalse.s loc_38457
0x3843c  ldarg.0
0x3843d  ldc.i4.s 0x11
0x3843f  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_LabelType(int32 value)
0x38444  ldarg.0
0x38445  ldarg.0
0x38446  ldarg.1
0x38447  ldarg.2
0x38448  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.LocalizedLabelDescription::GetObjectIdForManagedProperty(class [System.Xml]System.Xml.XmlNode node, bool throwIfIdsMissing)
0x3844d  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectId(valuetype [mscorlib]System.Guid value)
0x38452  br       loc_38582
0x38457  ldarg.1
0x38458  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x3845d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x38462  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x38467  ldstr    aOption// "option"
0x3846c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x38471  brtrue.s loc_384AE
0x38473  ldarg.1
0x38474  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x38479  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x3847e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x38483  ldstr    aState// "state"
0x38488  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3848d  brtrue.s loc_384AE
0x3848f  ldarg.1
0x38490  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x38495  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x3849a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x3849f  ldstr    aStatus// "status"
0x384a4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x384a9  brfalse  loc_38582
0x384ae  ldarg.0
0x384af  ldc.i4.2
0x384b0  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_LabelType(int32 value)
0x384b5  ldarg.0
0x384b6  ldarg.0
0x384b7  ldarg.1
0x384b8  ldarg.2
0x384b9  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.LocalizedLabelDescription::GetObjectIdForAttributePicklistValue(class [System.Xml]System.Xml.XmlNode node, bool throwIfIdsMissing)
0x384be  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectId(valuetype [mscorlib]System.Guid value)
0x384c3  br       loc_38582
0x384c8  ldarg.0
0x384c9  ldstr    aColor// "Color"
0x384ce  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectColumnName(string value)
0x384d3  ldarg.0
0x384d4  ldc.i4.2
0x384d5  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_LabelType(int32 value)
0x384da  ldarg.0
0x384db  ldarg.0
0x384dc  ldarg.1
0x384dd  ldarg.2
0x384de  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.LocalizedLabelDescription::GetObjectIdForAttributePicklistValue(class [System.Xml]System.Xml.XmlNode node, bool throwIfIdsMissing)
0x384e3  callvirt instance void Microsoft.Crm.Metadata.LocalizedLabelDescription::set_ObjectId(valuetype [mscorlib]System.Guid value)
  ... truncated ...
```
