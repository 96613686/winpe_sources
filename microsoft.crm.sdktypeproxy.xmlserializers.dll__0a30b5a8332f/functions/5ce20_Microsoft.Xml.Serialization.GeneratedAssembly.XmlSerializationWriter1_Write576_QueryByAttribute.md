# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write576_QueryByAttribute

- ea: `0x5ce20`
- end: `0x5cfa4`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write576_QueryByAttribute`
- size: `388`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6600`
- `0x6ac0`

## callees

- `0x67f0`
- `0x6ac0`
- `0x3d110`
- `0x46740`
- `0x5ce20`

## string_xrefs

- `0x5ce65`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x5ce75`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x5ce8b`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x5cead`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x5cec3`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x5cef0`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x5cf07`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x5cf30`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x5cf54`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x5cf6b`: `http://schemas.microsoft.com/crm/2006/Query`

## pseudocode

```c

```

## disassembly

```asm
0x5ce20  ldarg.3
0x5ce21  brtrue.s loc_5CE30
0x5ce23  ldarg.s  4
0x5ce25  brfalse.s loc_5CE2F
0x5ce27  ldarg.0
0x5ce28  ldarg.1
0x5ce29  ldarg.2
0x5ce2a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x5ce2f  ret
0x5ce30  ldarg.s  5
0x5ce32  brtrue.s loc_5CE50
0x5ce34  ldarg.3
0x5ce35  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5ce3a  stloc.0
0x5ce3b  ldloc.0
0x5ce3c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryByAttribute
0x5ce41  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5ce46  beq.s    loc_5CE50
0x5ce48  ldarg.0
0x5ce49  ldarg.3
0x5ce4a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x5ce4f  throw
0x5ce50  ldarg.0
0x5ce51  ldarg.1
0x5ce52  ldarg.2
0x5ce53  ldarg.3
0x5ce54  ldc.i4.0
0x5ce55  ldnull
0x5ce56  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x5ce5b  ldarg.s  5
0x5ce5d  brfalse.s loc_5CE6F
0x5ce5f  ldarg.0
0x5ce60  ldstr    aQuerybyattribu// "QueryByAttribute"
0x5ce65  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x5ce6a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x5ce6f  ldarg.0
0x5ce70  ldstr    aEntityname_0// "EntityName"
0x5ce75  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x5ce7a  ldarg.3
0x5ce7b  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_EntityName()
0x5ce80  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x5ce85  ldarg.0
0x5ce86  ldstr    aColumnset_0// "ColumnSet"
0x5ce8b  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x5ce90  ldarg.3
0x5ce91  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x5ce96  ldc.i4.0
0x5ce97  ldc.i4.0
0x5ce98  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write565_ColumnSetBase(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase o, bool isNullable, bool needType)
0x5ce9d  ldarg.3
0x5ce9e  callvirt instance string[] [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryByAttribute::get_Attributes()
0x5cea3  stloc.1
0x5cea4  ldloc.1
0x5cea5  brfalse.s loc_5CEE0
0x5cea7  ldarg.0
0x5cea8  ldstr    aAttributes// "Attributes"
0x5cead  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x5ceb2  ldnull
0x5ceb3  ldc.i4.0
0x5ceb4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x5ceb9  ldc.i4.0
0x5ceba  stloc.2
0x5cebb  br.s     loc_5CED4
0x5cebd  ldarg.0
0x5cebe  ldstr    aAttribute// "Attribute"
0x5cec3  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x5cec8  ldloc.1
0x5cec9  ldloc.2
0x5ceca  ldelem.ref
0x5cecb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x5ced0  ldloc.2
0x5ced1  ldc.i4.1
0x5ced2  add
0x5ced3  stloc.2
0x5ced4  ldloc.2
0x5ced5  ldloc.1
0x5ced6  ldlen
0x5ced7  conv.i4
0x5ced8  blt.s    loc_5CEBD
0x5ceda  ldarg.0
0x5cedb  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x5cee0  ldarg.3
0x5cee1  callvirt instance object[] [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryByAttribute::get_Values()
0x5cee6  stloc.3
0x5cee7  ldloc.3
0x5cee8  brfalse.s loc_5CF2A
0x5ceea  ldarg.0
0x5ceeb  ldstr    aValues// "Values"
0x5cef0  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x5cef5  ldnull
0x5cef6  ldc.i4.0
0x5cef7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x5cefc  ldc.i4.0
0x5cefd  stloc.s  4
0x5ceff  br.s     loc_5CF1D
0x5cf01  ldarg.0
0x5cf02  ldstr    aValue// "Value"
0x5cf07  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x5cf0c  ldloc.3
0x5cf0d  ldloc.s  4
0x5cf0f  ldelem.ref
0x5cf10  ldc.i4.1
0x5cf11  ldc.i4.0
0x5cf12  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write123_Object(string n, string ns, object o, bool isNullable, bool needType)
0x5cf17  ldloc.s  4
0x5cf19  ldc.i4.1
0x5cf1a  add
0x5cf1b  stloc.s  4
0x5cf1d  ldloc.s  4
0x5cf1f  ldloc.3
0x5cf20  ldlen
0x5cf21  conv.i4
0x5cf22  blt.s    loc_5CF01
0x5cf24  ldarg.0
0x5cf25  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x5cf2a  ldarg.0
0x5cf2b  ldstr    aPageinfo// "PageInfo"
0x5cf30  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x5cf35  ldarg.3
0x5cf36  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.PagingInfo [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryByAttribute::get_PageInfo()
0x5cf3b  ldc.i4.0
0x5cf3c  ldc.i4.0
0x5cf3d  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write566_PagingInfo(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.PagingInfo o, bool isNullable, bool needType)
0x5cf42  ldarg.3
0x5cf43  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryByAttribute::get_Orders()
0x5cf48  stloc.s  5
0x5cf4a  ldloc.s  5
0x5cf4c  brfalse.s loc_5CF9C
0x5cf4e  ldarg.0
0x5cf4f  ldstr    aOrders// "Orders"
0x5cf54  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x5cf59  ldnull
0x5cf5a  ldc.i4.0
0x5cf5b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x5cf60  ldc.i4.0
0x5cf61  stloc.s  6
0x5cf63  br.s     loc_5CF8B
0x5cf65  ldarg.0
0x5cf66  ldstr    aOrder// "Order"
0x5cf6b  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x5cf70  ldloc.s  5
0x5cf72  ldloc.s  6
0x5cf74  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x5cf79  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.OrderExpression
0x5cf7e  ldc.i4.0
0x5cf7f  ldc.i4.0
0x5cf80  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write574_OrderExpression(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.OrderExpression o, bool isNullable, bool needType)
0x5cf85  ldloc.s  6
0x5cf87  ldc.i4.1
0x5cf88  add
0x5cf89  stloc.s  6
0x5cf8b  ldloc.s  6
0x5cf8d  ldloc.s  5
0x5cf8f  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x5cf94  blt.s    loc_5CF65
0x5cf96  ldarg.0
0x5cf97  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x5cf9c  ldarg.0
0x5cf9d  ldarg.3
0x5cf9e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x5cfa3  ret
```
