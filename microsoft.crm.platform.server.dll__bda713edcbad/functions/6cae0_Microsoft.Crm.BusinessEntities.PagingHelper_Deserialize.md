# Microsoft.Crm.BusinessEntities.PagingHelper::Deserialize

- ea: `0x6cae0`
- end: `0x6cd05`
- name: `Microsoft.Crm.BusinessEntities.PagingHelper::Deserialize`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6c660`

## callees

- `0x1d320`
- `0x1d330`
- `0x1d3c0`
- `0x1d3d0`
- `0x1d3e0`
- `0x1d400`
- `0x6cae0`
- `0x6cd10`
- `0x90460`
- `0x90480`

## string_xrefs

- `0x6cba2`: `Malformed XML Passed to in the Paging Cookie. We expect at most two attributes (first/firstNull and last/lastNull)`
- `0x6cbea`: `Malformed XML Passed to in the Paging Cookie. Value for attribute first was not specified, and it was not null either.`
- `0x6cc35`: `Malformed XML Passed to in the Paging Cookie. Value for attribute last was not specified, and it was not null either.`
- `0x6ccb7`: `Malformed XML in the Paging Cookie`

## pseudocode

```c

```

## disassembly

```asm
0x6cae0  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x6cae5  stloc.0
0x6cae6  ldarg.1
0x6cae7  call     class [System.Xml]System.Xml.XmlReader [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlReader(string)
0x6caec  stloc.1
0x6caed  ldloc.1
0x6caee  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x6caf3  pop
0x6caf4  ldloc.1
0x6caf5  ldstr    aPage// "page"
0x6cafa  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x6caff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6cb04  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x6cb09  stloc.2
0x6cb0a  ldarg.s  4
0x6cb0c  ldarg.0
0x6cb0d  ldloc.1
0x6cb0e  call     instance class ParentEntityCondition Microsoft.Crm.BusinessEntities.PagingHelper::PopulateParentEntityCondition(class [System.Xml]System.Xml.XmlReader reader)
0x6cb13  stind.ref
0x6cb14  ldloc.2
0x6cb15  ldstr    aCookiepagenum// "cookiepagenum"
0x6cb1a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNegative(int32, string)
0x6cb1f  ldarg.2
0x6cb20  callvirt instance int32 Microsoft.Crm.Query.PagingInfo::get_PageNumber()
0x6cb25  stloc.3
0x6cb26  ldloc.2
0x6cb27  ldloc.3
0x6cb28  sub
0x6cb29  stloc.s  4
0x6cb2b  ldarg.2
0x6cb2c  ldloc.s  4
0x6cb2e  callvirt instance void Microsoft.Crm.Query.PagingInfo::set_PageBack(int32 value)
0x6cb33  ldloc.s  4
0x6cb35  ldc.i4.0
0x6cb36  ble.s    loc_6CB44
0x6cb38  ldarg.2
0x6cb39  ldc.i4.1
0x6cb3a  callvirt instance void Microsoft.Crm.Query.PagingInfo::set_UseOldPaging(bool value)
0x6cb3f  br       loc_6CC79
0x6cb44  ldloc.s  4
0x6cb46  ldc.i4.0
0x6cb47  bge      loc_6CC79
0x6cb4c  ldloc.s  4
0x6cb4e  ldc.i4.m1
0x6cb4f  bge      loc_6CC79
0x6cb54  ldarg.2
0x6cb55  ldloc.2
0x6cb56  callvirt instance void Microsoft.Crm.Query.PagingInfo::set_StartAfterPage(int32 value)
0x6cb5b  ldarg.2
0x6cb5c  dup
0x6cb5d  callvirt instance int32 Microsoft.Crm.Query.PagingInfo::get_PageNumber()
0x6cb62  ldarg.2
0x6cb63  callvirt instance int32 Microsoft.Crm.Query.PagingInfo::get_StartAfterPage()
0x6cb68  sub
0x6cb69  callvirt instance void Microsoft.Crm.Query.PagingInfo::set_PageNumber(int32 value)
0x6cb6e  ldarg.2
0x6cb6f  ldc.i4.1
0x6cb70  callvirt instance void Microsoft.Crm.Query.PagingInfo::set_UseOldPaging(bool value)
0x6cb75  br       loc_6CC79
0x6cb7a  ldloc.1
0x6cb7b  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x6cb80  ldc.i4.s 0xF
0x6cb82  beq      loc_6CC79
0x6cb87  ldloc.1
0x6cb88  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x6cb8d  stloc.s  5
0x6cb8f  ldarg.3
0x6cb90  ldloc.s  5
0x6cb92  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x6cb97  stloc.s  6
0x6cb99  ldloc.1
0x6cb9a  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_AttributeCount()
0x6cb9f  ldc.i4.2
0x6cba0  beq.s    loc_6CBB2
0x6cba2  ldstr    aMalformedXmlPa// "Malformed XML Passed to in the Paging C"...
0x6cba7  ldc.i4   0x80040201
0x6cbac  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x6cbb1  throw
0x6cbb2  ldloc.1
0x6cbb3  ldstr    aFirst// "first"
0x6cbb8  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x6cbbd  stloc.s  7
0x6cbbf  ldloc.1
0x6cbc0  ldstr    aLast// "last"
0x6cbc5  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x6cbca  stloc.s  8
0x6cbcc  ldloca.s 9
0x6cbce  initobj  OrderByPair
0x6cbd4  ldloc.s  7
0x6cbd6  brtrue.s loc_6CC0F
0x6cbd8  ldloc.1
0x6cbd9  ldstr    aFirstnull// "firstnull"
0x6cbde  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x6cbe3  brtrue.s loc_6CC05
0x6cbe5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6cbea  ldstr    aMalformedXmlPa_0// "Malformed XML Passed to in the Paging C"...
0x6cbef  ldc.i4.0
0x6cbf0  newarr   [mscorlib]System.Object
0x6cbf5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6cbfa  ldc.i4   0x80040201
0x6cbff  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x6cc04  throw
0x6cc05  ldloca.s 9
0x6cc07  ldnull
0x6cc08  call     instance void OrderByPair::set_First(object value)
0x6cc0d  br.s     loc_6CC1F
0x6cc0f  ldloca.s 9
0x6cc11  ldloc.s  6
0x6cc13  ldloc.s  7
0x6cc15  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::FromXmlString(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, string)
0x6cc1a  call     instance void OrderByPair::set_First(object value)
0x6cc1f  ldloc.s  8
0x6cc21  brtrue.s loc_6CC5A
0x6cc23  ldloc.1
0x6cc24  ldstr    aLastnull// "lastnull"
0x6cc29  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x6cc2e  brtrue.s loc_6CC50
0x6cc30  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6cc35  ldstr    aMalformedXmlPa_1// "Malformed XML Passed to in the Paging C"...
0x6cc3a  ldc.i4.0
0x6cc3b  newarr   [mscorlib]System.Object
0x6cc40  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6cc45  ldc.i4   0x80040201
0x6cc4a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x6cc4f  throw
0x6cc50  ldloca.s 9
0x6cc52  ldnull
0x6cc53  call     instance void OrderByPair::set_Last(object value)
0x6cc58  br.s     loc_6CC6A
0x6cc5a  ldloca.s 9
0x6cc5c  ldloc.s  6
0x6cc5e  ldloc.s  8
0x6cc60  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ConvertHelper::FromXmlString(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, string)
0x6cc65  call     instance void OrderByPair::set_Last(object value)
0x6cc6a  ldloc.0
0x6cc6b  ldloc.s  5
0x6cc6d  ldloc.s  9
0x6cc6f  box      OrderByPair
0x6cc74  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x6cc79  ldloc.1
0x6cc7a  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x6cc7f  brtrue   loc_6CB7A
0x6cc84  leave.s  loc_6CC90
0x6cc86  ldloc.1
0x6cc87  brfalse.s loc_6CC8F
0x6cc89  ldloc.1
0x6cc8a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6cc8f  endfinally
0x6cc90  leave.s  loc_6CD03
0x6cc92  stloc.s  0xA
0x6cc94  ldloc.s  0xA
0x6cc96  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x6cc9b  ldc.i4.s 0x14
0x6cc9d  ldstr    a0// "{0}"
0x6cca2  ldc.i4.1
0x6cca3  newarr   [mscorlib]System.Object
0x6cca8  dup
0x6cca9  ldc.i4.0
0x6ccaa  ldloc.s  0xA
0x6ccac  stelem.ref
0x6ccad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6ccb2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6ccb7  ldstr    aMalformedXmlIn// "Malformed XML in the Paging Cookie"
0x6ccbc  ldc.i4.0
0x6ccbd  newarr   [mscorlib]System.Object
0x6ccc2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6ccc7  ldc.i4   0x80040201
0x6cccc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x6ccd1  throw
0x6ccd2  stloc.s  0xB
0x6ccd4  ldloc.s  0xB
0x6ccd6  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x6ccdb  ldc.i4.s 0x14
0x6ccdd  ldstr    a0// "{0}"
0x6cce2  ldc.i4.1
0x6cce3  newarr   [mscorlib]System.Object
0x6cce8  dup
0x6cce9  ldc.i4.0
0x6ccea  ldloc.s  0xB
0x6ccec  stelem.ref
0x6cced  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6ccf2  ldc.i4   0x8004112A
0x6ccf7  ldc.i4.0
0x6ccf8  newarr   [mscorlib]System.Object
0x6ccfd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x6cd02  throw
0x6cd03  ldloc.0
0x6cd04  ret
```
