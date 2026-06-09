# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write575_QueryExpression

- ea: `0x6670`
- end: `0x67e7`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write575_QueryExpression`
- size: `375`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6600`
- `0x6ac0`
- `0x63430`

## callees

- `0x6670`
- `0x67f0`
- `0x68d0`
- `0x184d0`
- `0x3d110`
- `0x46740`

## string_xrefs

- `0x66b5`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x66c5`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x66db`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x66f3`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x670e`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x6730`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x6746`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x6777`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x6799`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x67b0`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x6741`: `LinkEntity`
- `0x672b`: `LinkEntities`

## pseudocode

```c

```

## disassembly

```asm
0x6670  ldarg.3
0x6671  brtrue.s loc_6680
0x6673  ldarg.s  4
0x6675  brfalse.s loc_667F
0x6677  ldarg.0
0x6678  ldarg.1
0x6679  ldarg.2
0x667a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x667f  ret
0x6680  ldarg.s  5
0x6682  brtrue.s loc_66A0
0x6684  ldarg.3
0x6685  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x668a  stloc.0
0x668b  ldloc.0
0x668c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression
0x6691  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6696  beq.s    loc_66A0
0x6698  ldarg.0
0x6699  ldarg.3
0x669a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x669f  throw
0x66a0  ldarg.0
0x66a1  ldarg.1
0x66a2  ldarg.2
0x66a3  ldarg.3
0x66a4  ldc.i4.0
0x66a5  ldnull
0x66a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x66ab  ldarg.s  5
0x66ad  brfalse.s loc_66BF
0x66af  ldarg.0
0x66b0  ldstr    aQueryexpressio// "QueryExpression"
0x66b5  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x66ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x66bf  ldarg.0
0x66c0  ldstr    aEntityname_0// "EntityName"
0x66c5  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x66ca  ldarg.3
0x66cb  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_EntityName()
0x66d0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x66d5  ldarg.0
0x66d6  ldstr    aColumnset_0// "ColumnSet"
0x66db  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x66e0  ldarg.3
0x66e1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x66e6  ldc.i4.0
0x66e7  ldc.i4.0
0x66e8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write565_ColumnSetBase(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase o, bool isNullable, bool needType)
0x66ed  ldarg.0
0x66ee  ldstr    aDistinct// "Distinct"
0x66f3  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x66f8  ldarg.3
0x66f9  callvirt instance bool [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Distinct()
0x66fe  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x6703  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x6708  ldarg.0
0x6709  ldstr    aPageinfo// "PageInfo"
0x670e  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x6713  ldarg.3
0x6714  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.PagingInfo [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_PageInfo()
0x6719  ldc.i4.0
0x671a  ldc.i4.0
0x671b  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write566_PagingInfo(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.PagingInfo o, bool isNullable, bool needType)
0x6720  ldarg.3
0x6721  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_LinkEntities()
0x6726  stloc.1
0x6727  ldloc.1
0x6728  brfalse.s loc_6771
0x672a  ldarg.0
0x672b  ldstr    aLinkentities// "LinkEntities"
0x6730  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x6735  ldnull
0x6736  ldc.i4.0
0x6737  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x673c  ldc.i4.0
0x673d  stloc.2
0x673e  br.s     loc_6762
0x6740  ldarg.0
0x6741  ldstr    aLinkentity// "LinkEntity"
0x6746  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x674b  ldloc.1
0x674c  ldloc.2
0x674d  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x6752  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity
0x6757  ldc.i4.0
0x6758  ldc.i4.0
0x6759  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write572_LinkEntity(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity o, bool isNullable, bool needType)
0x675e  ldloc.2
0x675f  ldc.i4.1
0x6760  add
0x6761  stloc.2
0x6762  ldloc.2
0x6763  ldloc.1
0x6764  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x6769  blt.s    loc_6740
0x676b  ldarg.0
0x676c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x6771  ldarg.0
0x6772  ldstr    aCriteria// "Criteria"
0x6777  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x677c  ldarg.3
0x677d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x6782  ldc.i4.0
0x6783  ldc.i4.0
0x6784  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write571_FilterExpression(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression o, bool isNullable, bool needType)
0x6789  ldarg.3
0x678a  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Orders()
0x678f  stloc.3
0x6790  ldloc.3
0x6791  brfalse.s loc_67DF
0x6793  ldarg.0
0x6794  ldstr    aOrders// "Orders"
0x6799  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x679e  ldnull
0x679f  ldc.i4.0
0x67a0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x67a5  ldc.i4.0
0x67a6  stloc.s  4
0x67a8  br.s     loc_67CF
0x67aa  ldarg.0
0x67ab  ldstr    aOrder// "Order"
0x67b0  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x67b5  ldloc.3
0x67b6  ldloc.s  4
0x67b8  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x67bd  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.OrderExpression
0x67c2  ldc.i4.0
0x67c3  ldc.i4.0
0x67c4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write574_OrderExpression(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.OrderExpression o, bool isNullable, bool needType)
0x67c9  ldloc.s  4
0x67cb  ldc.i4.1
0x67cc  add
0x67cd  stloc.s  4
0x67cf  ldloc.s  4
0x67d1  ldloc.3
0x67d2  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x67d7  blt.s    loc_67AA
0x67d9  ldarg.0
0x67da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x67df  ldarg.0
0x67e0  ldarg.3
0x67e1  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x67e6  ret
```
