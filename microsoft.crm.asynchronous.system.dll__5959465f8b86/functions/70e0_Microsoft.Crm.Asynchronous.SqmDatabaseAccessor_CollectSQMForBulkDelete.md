# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSQMForBulkDelete

- ea: `0x70e0`
- end: `0x73d9`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSQMForBulkDelete`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x52d0`

## callees

- `0x70e0`
- `0xeb60`

## string_xrefs

- `0x70f6`: `select sum(SuccessCount+FailureCount) from bulkdeleteoperationbase group by bulkdeleteoperationbase.BulkDeleteOperationId`
- `0x712c`: `select sum(SuccessCount) from bulkdeleteoperationbase group by bulkdeleteoperationbase.BulkDeleteOperationId`
- `0x7162`: `select sum(FailureCount) from bulkdeleteoperationbase group by bulkdeleteoperationbase.BulkDeleteOperationId`
- `0x71bb`: `select distinct OrderedQuerySetXml from bulkdeleteoperationbase where bulkdeleteoperationbase.OrderedQuerySetXml is not null and bulkdeleteoperationbase.BulkDeleteOperationId is not null`

## pseudocode

```c

```

## disassembly

```asm
0x70e0  newobj   instance void <>c__DisplayClass32_0::.ctor()
0x70e5  stloc.0
0x70e6  ldloc.0
0x70e7  ldarg.1
0x70e8  stfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass32_0::session
0x70ed  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x70f2  stloc.s  8
0x70f4  ldloc.s  8
0x70f6  ldstr    aSelectSumSucce// "select sum(SuccessCount+FailureCount) f"...
0x70fb  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7100  ldarg.0
0x7101  ldloc.s  8
0x7103  ldloc.0
0x7104  ldftn    instance void <>c__DisplayClass32_0::<CollectSQMForBulkDelete>b__0(object[] values)
0x710a  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x710f  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7114  pop
0x7115  leave.s  loc_7123
0x7117  ldloc.s  8
0x7119  brfalse.s loc_7122
0x711b  ldloc.s  8
0x711d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7122  endfinally
0x7123  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x7128  stloc.s  9
0x712a  ldloc.s  9
0x712c  ldstr    aSelectSumSucce_0// "select sum(SuccessCount) from bulkdelet"...
0x7131  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x7136  ldarg.0
0x7137  ldloc.s  9
0x7139  ldloc.0
0x713a  ldftn    instance void <>c__DisplayClass32_0::<CollectSQMForBulkDelete>b__1(object[] values)
0x7140  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x7145  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x714a  pop
0x714b  leave.s  loc_7159
0x714d  ldloc.s  9
0x714f  brfalse.s loc_7158
0x7151  ldloc.s  9
0x7153  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7158  endfinally
0x7159  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x715e  stloc.s  0xA
0x7160  ldloc.s  0xA
0x7162  ldstr    aSelectSumFailu// "select sum(FailureCount) from bulkdelet"...
0x7167  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x716c  ldarg.0
0x716d  ldloc.s  0xA
0x716f  ldloc.0
0x7170  ldftn    instance void <>c__DisplayClass32_0::<CollectSQMForBulkDelete>b__2(object[] values)
0x7176  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x717b  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7180  pop
0x7181  leave.s  loc_718F
0x7183  ldloc.s  0xA
0x7185  brfalse.s loc_718E
0x7187  ldloc.s  0xA
0x7189  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x718e  endfinally
0x718f  ldnull
0x7190  stloc.1
0x7191  ldsfld   string [mscorlib]System.String::Empty
0x7196  stloc.2
0x7197  ldsfld   string [mscorlib]System.String::Empty
0x719c  stloc.3
0x719d  ldloc.0
0x719e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x71a3  stfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass32_0::orderedQuerySet
0x71a8  ldc.i4.m1
0x71a9  stloc.s  4
0x71ab  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::.ctor()
0x71b0  stloc.s  5
0x71b2  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x71b7  stloc.s  0xB
0x71b9  ldloc.s  0xB
0x71bb  ldstr    aSelectDistinct_1// "select distinct OrderedQuerySetXml from"...
0x71c0  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x71c5  ldarg.0
0x71c6  ldloc.s  0xB
0x71c8  ldloc.0
0x71c9  ldftn    instance void <>c__DisplayClass32_0::<CollectSQMForBulkDelete>b__3(object[] values)
0x71cf  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x71d4  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x71d9  pop
0x71da  leave.s  loc_71E8
0x71dc  ldloc.s  0xB
0x71de  brfalse.s loc_71E7
0x71e0  ldloc.s  0xB
0x71e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x71e7  endfinally
0x71e8  ldc.i4.0
0x71e9  stloc.s  0xC
0x71eb  br       loc_72E9
0x71f0  ldloc.0
0x71f1  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass32_0::orderedQuerySet
0x71f6  ldloc.s  0xC
0x71f8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x71fd  stloc.2
0x71fe  ldloc.2
0x71ff  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7204  brtrue.s loc_723C
0x7206  ldtoken  string[]
0x720b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x7210  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0x7215  stloc.s  0xD
0x7217  ldloc.2
0x7218  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x721d  stloc.s  0xE
0x721f  ldloc.s  0xD
0x7221  ldloc.s  0xE
0x7223  callvirt instance object [System.Xml]System.Xml.Serialization.XmlSerializer::Deserialize(class [mscorlib]System.IO.TextReader)
0x7228  castclass string[]
0x722d  stloc.1
0x722e  leave.s  loc_723C
0x7230  ldloc.s  0xE
0x7232  brfalse.s loc_723B
0x7234  ldloc.s  0xE
0x7236  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x723b  endfinally
0x723c  ldc.i4.0
0x723d  stloc.s  0xF
0x723f  br       loc_72D9
0x7244  ldloc.1
0x7245  ldloc.s  0xF
0x7247  ldelem.ref
0x7248  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x724d  ldstr    aFetchEntity// "fetch/entity"
0x7252  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x7257  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x725c  ldstr    aName// "name"
0x7261  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x7266  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x726b  stloc.3
0x726c  ldloc.3
0x726d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7272  brtrue.s loc_72D3
0x7274  ldarg.0
0x7275  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x727a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x727f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x7284  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7289  ldloc.3
0x728a  ldc.i4.1
0x728b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x7290  stloc.s  0x10
0x7292  ldloc.s  5
0x7294  ldloc.s  0x10
0x7296  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x729b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::ContainsKey(var<u1>)
0x72a0  brtrue.s loc_72B3
0x72a2  ldloc.s  5
0x72a4  ldloc.s  0x10
0x72a6  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x72ab  ldc.i4.0
0x72ac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::Add(var<u1>, !!T0)
0x72b1  br.s     loc_72D3
0x72b3  ldloc.s  5
0x72b5  ldloc.s  0x10
0x72b7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x72bc  stloc.s  0x11
0x72be  dup
0x72bf  ldloc.s  0x11
0x72c1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::get_Item(void)
0x72c6  stloc.s  0x12
0x72c8  ldloc.s  0x11
0x72ca  ldloc.s  0x12
0x72cc  ldc.i4.1
0x72cd  add
0x72ce  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::set_Item(var<u1>, !!T0)
0x72d3  ldloc.s  0xF
0x72d5  ldc.i4.1
0x72d6  add
0x72d7  stloc.s  0xF
0x72d9  ldloc.s  0xF
0x72db  ldloc.1
0x72dc  ldlen
0x72dd  conv.i4
0x72de  blt      loc_7244
0x72e3  ldloc.s  0xC
0x72e5  ldc.i4.1
0x72e6  add
0x72e7  stloc.s  0xC
0x72e9  ldloc.s  0xC
0x72eb  ldloc.0
0x72ec  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> <>c__DisplayClass32_0::orderedQuerySet
0x72f1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x72f6  blt      loc_71F0
0x72fb  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, int32>>::.ctor()
0x7300  stloc.s  6
0x7302  ldloc.s  5
0x7304  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::get_Keys()
0x7309  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<int32, int32>::GetEnumerator()
0x730e  stloc.s  0x13
0x7310  br.s     loc_7332
0x7312  ldloca.s 0x13
0x7314  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, int32>::get_Current()
0x7319  stloc.s  0x14
0x731b  ldloc.s  6
0x731d  ldloc.s  0x14
0x731f  ldloc.s  5
0x7321  ldloc.s  0x14
0x7323  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::get_Item(void)
0x7328  newobj   instance void valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, int32>::.ctor(var<u1>, !!T0)
0x732d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, int32>>::Add(var<u1>)
0x7332  ldloca.s 0x13
0x7334  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, int32>::MoveNext()
0x7339  brtrue.s loc_7312
0x733b  leave.s  loc_734B
0x733d  ldloca.s 0x13
0x733f  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<int32, int32>
0x7345  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x734a  endfinally
0x734b  ldloc.s  6
0x734d  ldsfld   class [mscorlib]System.Comparison`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, int32>> <>c::<>9__32_4
0x7352  dup
0x7353  brtrue.s loc_736C
0x7355  pop
0x7356  ldsfld   class <>c <>c::<>9
0x735b  ldftn    instance int32 <>c::<CollectSQMForBulkDelete>b__32_4(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, int32> A1, valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, int32> A2)
0x7361  newobj   instance void class [mscorlib]System.Comparison`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, int32>>::.ctor(object, native int)
0x7366  dup
0x7367  stsfld   class [mscorlib]System.Comparison`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, int32>> <>c::<>9__32_4
0x736c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, int32>>::Sort(class [mscorlib]System.Comparison`1<var<u1>>)
0x7371  ldloc.s  6
0x7373  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, int32>>::get_Count()
0x7378  ldc.i4.5
0x7379  blt.s    loc_7380
0x737b  ldc.i4.5
0x737c  stloc.s  4
0x737e  br.s     loc_7389
0x7380  ldloc.s  6
0x7382  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, int32>>::get_Count()
0x7387  stloc.s  4
0x7389  ldloc.s  4
0x738b  newarr   [mscorlib]System.Int32
0x7390  stloc.s  7
0x7392  ldc.i4.0
0x7393  stloc.s  0x15
0x7395  br.s     loc_73D2
0x7397  ldloc.s  7
0x7399  ldloc.s  0x15
0x739b  ldloc.s  6
0x739d  ldloc.s  0x15
0x739f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, int32>>::get_Item(!!T0)
0x73a4  stloc.s  0x16
0x73a6  ldloca.s 0x16
0x73a8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, int32>::get_Key()
0x73ad  stelem.i4
0x73ae  ldloc.0
0x73af  ldfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass32_0::session
0x73b4  ldc.i4   0xFE
0x73b9  ldc.i4.1
0x73ba  newarr   [mscorlib]System.Int32
0x73bf  dup
0x73c0  ldc.i4.0
0x73c1  ldloc.s  7
0x73c3  ldloc.s  0x15
0x73c5  ldelem.i4
0x73c6  stelem.i4
0x73c7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::AddToStream(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32[])
0x73cc  ldloc.s  0x15
0x73ce  ldc.i4.1
0x73cf  add
0x73d0  stloc.s  0x15
0x73d2  ldloc.s  0x15
0x73d4  ldloc.s  4
0x73d6  blt.s    loc_7397
0x73d8  ret
```
