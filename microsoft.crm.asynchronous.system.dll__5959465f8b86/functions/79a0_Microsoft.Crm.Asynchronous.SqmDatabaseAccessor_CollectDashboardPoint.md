# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectDashboardPoint

- ea: `0x79a0`
- end: `0x7b10`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectDashboardPoint`
- size: `368`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xef50`
- `0xef70`

## callees

- `0x79a0`

## string_xrefs

- `0x79dc`: `classid`

## pseudocode

```c

```

## disassembly

```asm
0x79a0  ldarg.2
0x79a1  ldc.i4.0
0x79a2  ldelem.ref
0x79a3  castclass [mscorlib]System.String
0x79a8  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x79ad  ldstr    aFormTabsTabCon// "/form/tabs/tab//control"
0x79b2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x79b7  stloc.0
0x79b8  ldloc.0
0x79b9  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x79be  stloc.1
0x79bf  br       loc_7AE4
0x79c4  ldloc.1
0x79c5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x79ca  castclass [System.Xml]System.Xml.XmlNode
0x79cf  stloc.2
0x79d0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x79d5  stloc.3
0x79d6  ldloc.2
0x79d7  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x79dc  ldstr    aClassid// "classid"
0x79e1  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x79e6  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x79eb  ldloca.s 3
0x79ed  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x79f2  brfalse  loc_7AE4
0x79f7  ldloca.s 3
0x79f9  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormConstants::FrameControlClassId
0x79fe  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x7a03  brfalse.s loc_7A26
0x7a05  ldarg.1
0x7a06  dup
0x7a07  ldc.i4   0x20D
0x7a0c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x7a11  stloc.s  4
0x7a13  ldc.i4   0x20D
0x7a18  ldloc.s  4
0x7a1a  ldc.i4.1
0x7a1b  add
0x7a1c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x7a21  br       loc_7AE4
0x7a26  ldloca.s 3
0x7a28  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormConstants::WebResourceHtmlControlClassId
0x7a2d  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x7a32  brtrue.s loc_7A50
0x7a34  ldloca.s 3
0x7a36  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormConstants::WebResourceImageControlClassId
0x7a3b  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x7a40  brtrue.s loc_7A50
0x7a42  ldloca.s 3
0x7a44  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormConstants::WebResourceSilverlightControlClassId
0x7a49  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x7a4e  brfalse.s loc_7A6E
0x7a50  ldarg.1
0x7a51  dup
0x7a52  ldc.i4   0x20E
0x7a57  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x7a5c  stloc.s  4
0x7a5e  ldc.i4   0x20E
0x7a63  ldloc.s  4
0x7a65  ldc.i4.1
0x7a66  add
0x7a67  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x7a6c  br.s     loc_7AE4
0x7a6e  ldloca.s 3
0x7a70  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormConstants::GridControlClassId
0x7a75  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x7a7a  brfalse.s loc_7AE4
0x7a7c  ldloc.2
0x7a7d  ldstr    aParametersChar// "parameters/ChartGridMode"
0x7a82  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x7a87  stloc.s  5
0x7a89  ldloc.s  5
0x7a8b  brfalse.s loc_7AC8
0x7a8d  ldloc.s  5
0x7a8f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x7a94  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7a99  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x7a9e  ldstr    aChart// "CHART"
0x7aa3  callvirt instance bool [mscorlib]System.String::Equals(string)
0x7aa8  brfalse.s loc_7AC8
0x7aaa  ldarg.1
0x7aab  dup
0x7aac  ldc.i4   0x20B
0x7ab1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x7ab6  stloc.s  4
0x7ab8  ldc.i4   0x20B
0x7abd  ldloc.s  4
0x7abf  ldc.i4.1
0x7ac0  add
0x7ac1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x7ac6  br.s     loc_7AE4
0x7ac8  ldarg.1
0x7ac9  dup
0x7aca  ldc.i4   0x20C
0x7acf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x7ad4  stloc.s  4
0x7ad6  ldc.i4   0x20C
0x7adb  ldloc.s  4
0x7add  ldc.i4.1
0x7ade  add
0x7adf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x7ae4  ldloc.1
0x7ae5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7aea  brtrue   loc_79C4
0x7aef  leave.s  loc_7B0F
0x7af1  ldloc.1
0x7af2  isinst   [mscorlib]System.IDisposable
0x7af7  stloc.s  6
0x7af9  ldloc.s  6
0x7afb  brfalse.s loc_7B04
0x7afd  ldloc.s  6
0x7aff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7b04  endfinally
0x7b05  ldloc.0
0x7b06  brfalse.s loc_7B0E
0x7b08  ldloc.0
0x7b09  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7b0e  endfinally
0x7b0f  ret
```
