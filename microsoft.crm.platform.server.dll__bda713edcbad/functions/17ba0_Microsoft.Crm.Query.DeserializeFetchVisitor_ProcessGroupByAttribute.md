# Microsoft.Crm.Query.DeserializeFetchVisitor::ProcessGroupByAttribute

- ea: `0x17ba0`
- end: `0x17c90`
- name: `Microsoft.Crm.Query.DeserializeFetchVisitor::ProcessGroupByAttribute`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16600`

## callees

- `0x13250`
- `0x13330`
- `0x13460`
- `0x13540`
- `0x17a90`
- `0x17ba0`
- `0x17db0`
- `0x52e60`
- `0x52eb0`

## string_xrefs

- `0x17bc4`: `groupby cannot be specified if aggreate is not true. NodeXml: {0}`
- `0x17c6b`: `groupby cannot be specified for attribute type MultiSelectPickList. NodeXml: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x17ba0  ldarg.2
0x17ba1  ldstr    aGroupby// "groupby"
0x17ba6  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x17bab  stloc.0
0x17bac  ldloc.0
0x17bad  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17bb2  brtrue   loc_17C8F
0x17bb7  ldarg.0
0x17bb8  ldfld    bool Microsoft.Crm.Query.DeserializeFetchVisitor::bHasAggregate
0x17bbd  brtrue.s loc_17BE8
0x17bbf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17bc4  ldstr    aGroupbyCannotB// "groupby cannot be specified if aggreate"...
0x17bc9  ldc.i4.1
0x17bca  newarr   [mscorlib]System.Object
0x17bcf  dup
0x17bd0  ldc.i4.0
0x17bd1  ldarg.2
0x17bd2  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::OuterXml(class [System.Xml.Linq]System.Xml.Linq.XNode node)
0x17bd7  stelem.ref
0x17bd8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17bdd  ldc.i4   0x8004112E
0x17be2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x17be7  throw
0x17be8  ldarg.1
0x17be9  ldarg.0
0x17bea  ldloc.0
0x17beb  ldarg.2
0x17bec  ldc.i4   0x8004112E
0x17bf1  call     instance bool Microsoft.Crm.Query.DeserializeFetchVisitor::ParseFetchBool(string boolString, class [System.Xml.Linq]System.Xml.Linq.XElement node, int32 errorCode)
0x17bf6  callvirt instance void Microsoft.Crm.Query.AttributeExpression::set_HasGroupBy(bool value)
0x17bfb  ldarg.1
0x17bfc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Query.AttributeExpression::get_Attribute()
0x17c01  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x17c06  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x17c0b  stloc.1
0x17c0c  ldloc.1
0x17c0d  ldc.i4.2
0x17c0e  beq.s    loc_17C16
0x17c10  ldloc.1
0x17c11  ldc.i4.s 0x17
0x17c13  beq.s    loc_17C66
0x17c15  ret
0x17c16  ldarg.2
0x17c17  ldstr    aDategrouping// "dategrouping"
0x17c1c  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x17c21  stloc.2
0x17c22  ldarg.0
0x17c23  ldloc.2
0x17c24  call     instance valuetype Microsoft.Crm.Query.DateTimeGroupingType Microsoft.Crm.Query.DeserializeFetchVisitor::GetDateGrouping(string dategrouping)
0x17c29  ldarg.2
0x17c2a  ldstr    aUsertimezone// "usertimezone"
0x17c2f  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::TryGetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XElement node, string attributeName)
0x17c34  stloc.3
0x17c35  ldc.i4.1
0x17c36  stloc.s  4
0x17c38  ldloc.3
0x17c39  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17c3e  brtrue.s loc_17C51
0x17c40  ldarg.0
0x17c41  ldloc.3
0x17c42  ldarg.2
0x17c43  ldc.i4   0x80041101
0x17c48  call     instance bool Microsoft.Crm.Query.DeserializeFetchVisitor::ParseFetchBool(string boolString, class [System.Xml.Linq]System.Xml.Linq.XElement node, int32 errorCode)
0x17c4d  stloc.s  4
0x17c4f  br.s     loc_17C54
0x17c51  ldc.i4.1
0x17c52  stloc.s  4
0x17c54  ldloc.s  4
0x17c56  newobj   instance void Microsoft.Crm.Query.DateTimeGroupingInfo::.ctor(valuetype Microsoft.Crm.Query.DateTimeGroupingType type, bool useUserTimeZone)
0x17c5b  stloc.s  5
0x17c5d  ldarg.1
0x17c5e  ldloc.s  5
0x17c60  callvirt instance void Microsoft.Crm.Query.AttributeExpression::set_DateTimeGroupingInfo(class Microsoft.Crm.Query.DateTimeGroupingInfo value)
0x17c65  ret
0x17c66  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17c6b  ldstr    aGroupbyCannotB_0// "groupby cannot be specified for attribu"...
0x17c70  ldc.i4.1
0x17c71  newarr   [mscorlib]System.Object
0x17c76  dup
0x17c77  ldc.i4.0
0x17c78  ldarg.2
0x17c79  call     string Microsoft.Crm.Platform.Server.Utility.XmlHelper::OuterXml(class [System.Xml.Linq]System.Xml.Linq.XNode node)
0x17c7e  stelem.ref
0x17c7f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17c84  ldc.i4   0x80050224
0x17c89  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x17c8e  throw
0x17c8f  ret
```
