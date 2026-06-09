# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSqmForGrouping

- ea: `0x8070`
- end: `0x8219`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSqmForGrouping`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7cf0`

## callees

- `0x8070`

## pseudocode

```c

```

## disassembly

```asm
0x8070  ldarg.2
0x8071  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x8076  ldc.i4.1
0x8077  ble.s    loc_8093
0x8079  ldarg.1
0x807a  dup
0x807b  ldc.i4   0x200
0x8080  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x8085  stloc.1
0x8086  ldc.i4   0x200
0x808b  ldloc.1
0x808c  ldc.i4.1
0x808d  add
0x808e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x8093  ldarg.0
0x8094  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x8099  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x809e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x80a3  stloc.0
0x80a4  ldarg.2
0x80a5  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x80aa  stloc.2
0x80ab  br       loc_81F7
0x80b0  ldloc.2
0x80b1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x80b6  castclass [System.Xml]System.Xml.XmlNode
0x80bb  dup
0x80bc  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x80c1  ldstr    aName// "name"
0x80c6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x80cb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x80d0  stloc.3
0x80d1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x80d6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x80db  ldstr    aName// "name"
0x80e0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x80e5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x80ea  stloc.s  4
0x80ec  ldloc.0
0x80ed  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x80f2  ldloc.s  4
0x80f4  ldc.i4.1
0x80f5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x80fa  stloc.s  5
0x80fc  ldloc.s  5
0x80fe  brtrue.s loc_8105
0x8100  leave    loc_8218
0x8105  ldloc.s  5
0x8107  ldloc.3
0x8108  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x810d  stloc.s  6
0x810f  ldloc.s  6
0x8111  brtrue.s loc_8118
0x8113  leave    loc_8218
0x8118  ldloc.s  6
0x811a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x811f  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x8124  stloc.s  7
0x8126  ldloc.s  7
0x8128  ldc.i4.1
0x8129  sub
0x812a  switch   loc_8189, loc_81C1, loc_81DD, loc_81DD, loc_81DD, loc_81DD, loc_8189, loc_81DD, loc_81DD, loc_81A5, loc_81DD, loc_816D, loc_8189, loc_816D, loc_816D
0x816b  br.s     loc_81DD
0x816d  ldarg.1
0x816e  dup
0x816f  ldc.i4   0x207
0x8174  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x8179  stloc.1
0x817a  ldc.i4   0x207
0x817f  ldloc.1
0x8180  ldc.i4.1
0x8181  add
0x8182  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x8187  br.s     loc_81F7
0x8189  ldarg.1
0x818a  dup
0x818b  ldc.i4   0x208
0x8190  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x8195  stloc.1
0x8196  ldc.i4   0x208
0x819b  ldloc.1
0x819c  ldc.i4.1
0x819d  add
0x819e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x81a3  br.s     loc_81F7
0x81a5  ldarg.1
0x81a6  dup
0x81a7  ldc.i4   0x20A
0x81ac  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x81b1  stloc.1
0x81b2  ldc.i4   0x20A
0x81b7  ldloc.1
0x81b8  ldc.i4.1
0x81b9  add
0x81ba  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x81bf  br.s     loc_81F7
0x81c1  ldarg.1
0x81c2  dup
0x81c3  ldc.i4   0x209
0x81c8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x81cd  stloc.1
0x81ce  ldc.i4   0x209
0x81d3  ldloc.1
0x81d4  ldc.i4.1
0x81d5  add
0x81d6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x81db  br.s     loc_81F7
0x81dd  ldarg.1
0x81de  dup
0x81df  ldc.i4   0x210
0x81e4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x81e9  stloc.1
0x81ea  ldc.i4   0x210
0x81ef  ldloc.1
0x81f0  ldc.i4.1
0x81f1  add
0x81f2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x81f7  ldloc.2
0x81f8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x81fd  brtrue   loc_80B0
0x8202  leave.s  loc_8218
0x8204  ldloc.2
0x8205  isinst   [mscorlib]System.IDisposable
0x820a  stloc.s  8
0x820c  ldloc.s  8
0x820e  brfalse.s loc_8217
0x8210  ldloc.s  8
0x8212  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8217  endfinally
0x8218  ret
```
