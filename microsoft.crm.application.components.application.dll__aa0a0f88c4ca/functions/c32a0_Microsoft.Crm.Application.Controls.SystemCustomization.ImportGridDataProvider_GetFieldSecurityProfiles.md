# Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetFieldSecurityProfiles

- ea: `0xc32a0`
- end: `0xc33e0`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetFieldSecurityProfiles`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc0af0`

## callees

- `0xc32a0`
- `0xc3eb0`
- `0xf4210`

## string_xrefs

- `0xc32a1`: `EntityGridDataProvider_Types_FieldSecurityProfile`
- `0xc32ad`: `importexportxml/FieldSecurityProfiles/FieldSecurityProfile`
- `0xc3313`: `fieldsecurityprofile:`

## pseudocode

```c

```

## disassembly

```asm
0xc32a0  ldarg.1
0xc32a1  ldstr    aEntitygriddata_56// "EntityGridDataProvider_Types_FieldSecur"...
0xc32a6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc32ab  stloc.0
0xc32ac  ldarg.2
0xc32ad  ldstr    aImportexportxm_21// "importexportxml/FieldSecurityProfiles/F"...
0xc32b2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xc32b7  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xc32bc  stloc.2
0xc32bd  br       loc_C33BE
0xc32c2  ldloc.2
0xc32c3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xc32c8  castclass [System.Xml]System.Xml.XmlNode
0xc32cd  stloc.3
0xc32ce  ldloc.3
0xc32cf  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc32d4  ldstr    aName// "name"
0xc32d9  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xc32de  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xc32e3  stloc.s  4
0xc32e5  ldloc.3
0xc32e6  ldstr    aResult// "result"
0xc32eb  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xc32f0  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0xc32f5  stloc.s  5
0xc32f7  ldloc.s  5
0xc32f9  brfalse.s loc_C32FF
0xc32fb  ldloc.s  5
0xc32fd  br.s     loc_C3300
0xc32ff  ldc.i4.1
0xc3300  stloc.s  5
0xc3302  ldc.i4.0
0xc3303  stloc.s  6
0xc3305  br       loc_C33B5
0xc330a  ldc.i4.s 0xA
0xc330c  newarr   [mscorlib]System.String
0xc3311  dup
0xc3312  ldc.i4.0
0xc3313  ldstr    aFieldsecurityp_2// "fieldsecurityprofile:"
0xc3318  ldloc.3
0xc3319  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc331e  ldstr    aId_1// "id"
0xc3323  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xc3328  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xc332d  call     string [mscorlib]System.String::Concat(string, string)
0xc3332  stelem.ref
0xc3333  dup
0xc3334  ldc.i4.1
0xc3335  ldc.i4   0x4B0
0xc333a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc333f  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0xc3344  stelem.ref
0xc3345  dup
0xc3346  ldc.i4.2
0xc3347  ldloc.s  4
0xc3349  stelem.ref
0xc334a  dup
0xc334b  ldc.i4.3
0xc334c  ldloc.s  4
0xc334e  stelem.ref
0xc334f  dup
0xc3350  ldc.i4.4
0xc3351  ldloc.0
0xc3352  stelem.ref
0xc3353  dup
0xc3354  ldc.i4.5
0xc3355  ldloc.3
0xc3356  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xc335b  ldstr    aDescription// "description"
0xc3360  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xc3365  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xc336a  stelem.ref
0xc336b  dup
0xc336c  ldc.i4.6
0xc336d  ldloc.3
0xc336e  ldstr    aResult// "result"
0xc3373  ldloc.s  6
0xc3375  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p, int32 resultIndex)
0xc337a  stelem.ref
0xc337b  dup
0xc337c  ldc.i4.7
0xc337d  ldloc.3
0xc337e  ldstr    aDatetimeticks// "datetimeticks"
0xc3383  ldloc.s  6
0xc3385  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p, int32 resultIndex)
0xc338a  stelem.ref
0xc338b  dup
0xc338c  ldc.i4.8
0xc338d  ldloc.3
0xc338e  ldstr    aErrorcode_0// "errorcode"
0xc3393  ldloc.s  6
0xc3395  call     string Microsoft.Crm.Application.Controls.SystemCustomization.ImportGridDataProvider::GetResultNodeAttribute(class [System.Xml]System.Xml.XmlNode node, string p, int32 resultIndex)
0xc339a  stelem.ref
0xc339b  dup
0xc339c  ldc.i4.s 9
0xc339e  ldloc.s  4
0xc33a0  stelem.ref
0xc33a1  stloc.1
0xc33a2  ldarg.3
0xc33a3  ldloc.1
0xc33a4  newobj   instance void Row::.ctor(string[] columns)
0xc33a9  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xc33ae  pop
0xc33af  ldloc.s  6
0xc33b1  ldc.i4.1
0xc33b2  add
0xc33b3  stloc.s  6
0xc33b5  ldloc.s  6
0xc33b7  ldloc.s  5
0xc33b9  blt      loc_C330A
0xc33be  ldloc.2
0xc33bf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc33c4  brtrue   loc_C32C2
0xc33c9  leave.s  loc_C33DF
0xc33cb  ldloc.2
0xc33cc  isinst   [mscorlib]System.IDisposable
0xc33d1  stloc.s  7
0xc33d3  ldloc.s  7
0xc33d5  brfalse.s loc_C33DE
0xc33d7  ldloc.s  7
0xc33d9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc33de  endfinally
0xc33df  ret
```
