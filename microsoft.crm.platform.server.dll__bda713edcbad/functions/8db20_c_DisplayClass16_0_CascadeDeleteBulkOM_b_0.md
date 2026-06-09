# <>c__DisplayClass16_0::<CascadeDeleteBulkOM>b__0

- ea: `0x8db20`
- end: `0x8df52`
- name: `<>c__DisplayClass16_0::<CascadeDeleteBulkOM>b__0`
- size: `1074`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, installer_update`

## callees

- `0x1e6b0`
- `0x572d0`
- `0x57310`
- `0x5ed30`
- `0x5ef20`
- `0x5ef30`
- `0x5ef40`
- `0x5efa0`
- `0x5fbb0`
- `0x5fbd0`
- `0x5fbf0`
- `0x5fc10`
- `0x5fe30`
- `0x5fe50`
- `0x5fea0`
- `0x5ff30`
- `0x5ffb0`
- `0x66ae0`
- `0x78470`
- `0x8cf00`
- `0x8db20`

## string_xrefs

- `0x8dc83`: `update a set a.{1} = {2} from {0} a join @ids ids on a.{3} = ids.id`
- `0x8dd83`: `Unknown CascadeDeleteActionType enum value.`
- `0x8def9`: `Unknown CascadeDeleteActionType enum value.`
- `0x8df33`: `The entities to update list for which we execute action in bulk should be empty once we are done with the CascadeDelete. There must be at least one entitiy in the Delete list. Once we get to execute the Delete list, the entities to update list be empty which would mean that there are no left over entities still to be updated.`
- `0x8df46`: `Every entity that is in the Updated entities list should also be in the Deleted entities list.Once we are done with CascadeDekete we should have left an empty Updated entities list.`

## pseudocode

```c

```

## disassembly

```asm
0x8db20  ldarg.0
0x8db21  ldfld    class Microsoft.Crm.BusinessEntities.CascadeRecordSet <>c__DisplayClass16_0::collection
0x8db26  ldstr    aCollection// "collection"
0x8db2b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8db30  ldarg.0
0x8db31  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass16_0::context
0x8db36  ldstr    aContext// "context"
0x8db3b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8db40  ldarg.0
0x8db41  ldfld    class Microsoft.Crm.BusinessEntities.CascadeRecordSet <>c__DisplayClass16_0::collection
0x8db46  callvirt instance int32 Microsoft.Crm.BusinessEntities.CascadeRecordSet::get_Count()
0x8db4b  brtrue.s loc_8DB4E
0x8db4d  ret
0x8db4e  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype EntityKey>::.ctor()
0x8db53  stloc.0
0x8db54  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype EntityKey>::.ctor()
0x8db59  stloc.1
0x8db5a  ldc.i4.1
0x8db5b  stloc.2
0x8db5c  ldc.i4.m1
0x8db5d  stloc.3
0x8db5e  ldc.i4.m1
0x8db5f  stloc.s  4
0x8db61  ldarg.0
0x8db62  ldfld    class Microsoft.Crm.BusinessEntities.CascadeRecordSet <>c__DisplayClass16_0::collection
0x8db67  call     int32[] Microsoft.Crm.BusinessEntities.CascadeEngine::GetDeleteWithPipelineAndExtensionTypeCode(class Microsoft.Crm.BusinessEntities.CascadeRecordSet collection)
0x8db6c  ldarg.0
0x8db6d  ldfld    int32 <>c__DisplayClass16_0::parentEntityObjectTypeCode
0x8db72  ldarg.0
0x8db73  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass16_0::context
0x8db78  newobj   instance void Microsoft.Crm.BusinessEntities.CascadeDeletionHandler::.ctor(int32[] objectTypes, int32 rootComponentType, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8db7d  stloc.s  5
0x8db7f  ldc.i4.0
0x8db80  stloc.s  6
0x8db82  br       loc_8DF12
0x8db87  ldarg.0
0x8db88  ldfld    class Microsoft.Crm.BusinessEntities.CascadeRecordSet <>c__DisplayClass16_0::collection
0x8db8d  ldloc.s  6
0x8db8f  callvirt instance class Microsoft.Crm.BusinessEntities.CascadeRecord Microsoft.Crm.BusinessEntities.CascadeRecordSet::get_Item(int32 index)
0x8db94  stloc.s  7
0x8db96  ldarg.0
0x8db97  ldfld    bool <>c__DisplayClass16_0::cascadeDeleteChildEntityRecords
0x8db9c  brfalse.s loc_8DBC6
0x8db9e  ldloc.s  7
0x8dba0  brfalse.s loc_8DBC6
0x8dba2  ldarg.0
0x8dba3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass16_0::parentEntityIds
0x8dba8  ldloc.s  7
0x8dbaa  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.CascadeRecord::get_Id()
0x8dbaf  call     T0x2B00004D
0x8dbb4  ldc.i4.0
0x8dbb5  ceq
0x8dbb7  stloc.s  8
0x8dbb9  ldarg.0
0x8dbba  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass16_0::context
0x8dbbf  ldloc.s  8
0x8dbc1  call     void Microsoft.Crm.BusinessEntities.CascadeEngine::SetIsCascadeDeleteForChildEntityRecords(class Microsoft.Crm.BusinessEntities.ExecutionContext context, bool isCascadeDeleteForChildEntityRecords)
0x8dbc6  ldloc.s  7
0x8dbc8  callvirt instance valuetype Microsoft.Crm.BusinessEntities.CascadeDeleteActionType Microsoft.Crm.BusinessEntities.CascadeRecord::get_ActionType()
0x8dbcd  ldloc.2
0x8dbce  bge.s    loc_8DBE0
0x8dbd0  ldstr    aCascadeCollect// "Cascade Collect did not return records "...
0x8dbd5  ldstr    aRecordActionty// "record.ActionType"
0x8dbda  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x8dbdf  throw
0x8dbe0  ldloc.2
0x8dbe1  ldc.i4.1
0x8dbe2  sub
0x8dbe3  ldc.i4.1
0x8dbe4  ble.un.s loc_8DBF4
0x8dbe6  ldloc.2
0x8dbe7  ldc.i4.3
0x8dbe8  sub
0x8dbe9  ldc.i4.1
0x8dbea  ble.un   loc_8DD8E
0x8dbef  br       loc_8DD72
0x8dbf4  ldloc.s  4
0x8dbf6  ldloc.s  7
0x8dbf8  callvirt instance int32 Microsoft.Crm.BusinessEntities.CascadeRecord::get_AttributeColumnNumber()
0x8dbfd  bne.un.s loc_8DC16
0x8dbff  ldloc.3
0x8dc00  ldloc.s  7
0x8dc02  callvirt instance int32 Microsoft.Crm.BusinessEntities.CascadeRecord::get_ObjectTypeCode()
0x8dc07  bne.un.s loc_8DC16
0x8dc09  ldloc.s  7
0x8dc0b  callvirt instance valuetype Microsoft.Crm.BusinessEntities.CascadeDeleteActionType Microsoft.Crm.BusinessEntities.CascadeRecord::get_ActionType()
0x8dc10  ldloc.2
0x8dc11  beq      loc_8DD8E
0x8dc16  ldloc.1
0x8dc17  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype EntityKey>::get_Count()
0x8dc1c  brfalse  loc_8DD5F
0x8dc21  ldloc.3
0x8dc22  ldarg.0
0x8dc23  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass16_0::context
0x8dc28  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.CascadeEngine::GetEntityFromObjectTypeCode(int32 objectTypeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x8dc2d  stloc.s  9
0x8dc2f  ldloc.s  9
0x8dc31  ldloc.s  4
0x8dc33  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.BusinessEntities.CascadeEngine::GetAttributeFromEntityAndColumnNumber(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, int32 columnNumber)
0x8dc38  stloc.s  0xA
0x8dc3a  ldloc.s  0xA
0x8dc3c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsStoredOnPrimaryTable()
0x8dc41  brtrue.s loc_8DC4C
0x8dc43  ldloc.s  9
0x8dc45  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ExtensionTableName()
0x8dc4a  br.s     loc_8DC53
0x8dc4c  ldloc.s  9
0x8dc4e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_BaseTableName()
0x8dc53  stloc.s  0xB
0x8dc55  ldloc.s  0xA
0x8dc57  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsLogical()
0x8dc5c  ldc.i4.0
0x8dc5d  ceq
0x8dc5f  ldstr    aTheAttribute0I_0// "The attribute {0} in entity {1} should "...
0x8dc64  ldc.i4.2
0x8dc65  newarr   [mscorlib]System.Object
0x8dc6a  dup
0x8dc6b  ldc.i4.0
0x8dc6c  ldloc.s  0xA
0x8dc6e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x8dc73  stelem.ref
0x8dc74  dup
0x8dc75  ldc.i4.1
0x8dc76  ldloc.s  0xB
0x8dc78  stelem.ref
0x8dc79  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x8dc7e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8dc83  ldstr    aUpdateASetA12F// "update a set a.{1} = {2} from {0} a joi"...
0x8dc88  ldc.i4.4
0x8dc89  newarr   [mscorlib]System.Object
0x8dc8e  dup
0x8dc8f  ldc.i4.0
0x8dc90  ldloc.s  0xB
0x8dc92  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0x8dc97  stelem.ref
0x8dc98  dup
0x8dc99  ldc.i4.1
0x8dc9a  ldloc.s  0xA
0x8dc9c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x8dca1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0x8dca6  stelem.ref
0x8dca7  dup
0x8dca8  ldc.i4.2
0x8dca9  ldc.i4.2
0x8dcaa  ldloc.2
0x8dcab  beq.s    loc_8DCB4
0x8dcad  ldstr    aNull_2// "null"
0x8dcb2  br.s     loc_8DCCF
0x8dcb4  ldstr    aA// "a."
0x8dcb9  ldloc.s  9
0x8dcbb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x8dcc0  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x8dcc5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0x8dcca  call     string [mscorlib]System.String::Concat(string, string)
0x8dccf  stelem.ref
0x8dcd0  dup
0x8dcd1  ldc.i4.3
0x8dcd2  ldloc.s  9
0x8dcd4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x8dcd9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x8dcde  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0x8dce3  stelem.ref
0x8dce4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8dce9  stloc.s  0xC
0x8dceb  ldarg.0
0x8dcec  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass16_0::context
0x8dcf1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x8dcf6  ldloc.s  0xC
0x8dcf8  ldc.i4.1
0x8dcf9  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(string, bool)
0x8dcfe  stloc.s  0xD
0x8dd00  ldloc.s  0xD
0x8dd02  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x8dd07  ldloc.1
0x8dd08  ldsfld   class [mscorlib]System.Func`2<valuetype EntityKey, valuetype [mscorlib]System.Guid> <>c::<>9__16_1
0x8dd0d  dup
0x8dd0e  brtrue.s loc_8DD27
0x8dd10  pop
0x8dd11  ldsfld   class <>c <>c::<>9
0x8dd16  ldftn    instance valuetype [mscorlib]System.Guid <>c::<CascadeDeleteBulkOM>b__16_1(valuetype EntityKey value)
0x8dd1c  newobj   instance void class [mscorlib]System.Func`2<valuetype EntityKey, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x8dd21  dup
0x8dd22  stsfld   class [mscorlib]System.Func`2<valuetype EntityKey, valuetype [mscorlib]System.Guid> <>c::<>9__16_1
0x8dd27  call     T0x2B0000D1
0x8dd2c  ldstr    aIds_0// "@ids"
0x8dd31  call     class [System.Data]System.Data.SqlClient.SqlParameter Microsoft.Crm.Query.QueryHelper::GetEntityIdTableParameter(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> entityIds, string parameterName)
0x8dd36  callvirt instance int32 [mscorlib]System.Collections.IList::Add(object)
0x8dd3b  pop
0x8dd3c  ldloc.s  0xD
0x8dd3e  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x8dd43  pop
0x8dd44  leave.s  loc_8DD52
0x8dd46  ldloc.s  0xD
0x8dd48  brfalse.s loc_8DD51
0x8dd4a  ldloc.s  0xD
0x8dd4c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8dd51  endfinally
0x8dd52  ldloc.0
0x8dd53  ldloc.1
0x8dd54  callvirt instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype EntityKey>::UnionWith(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x8dd59  ldloc.1
0x8dd5a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype EntityKey>::Clear()
0x8dd5f  ldloc.s  7
0x8dd61  callvirt instance int32 Microsoft.Crm.BusinessEntities.CascadeRecord::get_ObjectTypeCode()
0x8dd66  stloc.3
0x8dd67  ldloc.s  7
0x8dd69  callvirt instance int32 Microsoft.Crm.BusinessEntities.CascadeRecord::get_AttributeColumnNumber()
0x8dd6e  stloc.s  4
0x8dd70  br.s     loc_8DD8E
0x8dd72  ldstr    aRecordActionty// "record.ActionType"
0x8dd77  ldloc.s  7
0x8dd79  callvirt instance valuetype Microsoft.Crm.BusinessEntities.CascadeDeleteActionType Microsoft.Crm.BusinessEntities.CascadeRecord::get_ActionType()
0x8dd7e  box      Microsoft.Crm.BusinessEntities.CascadeDeleteActionType
0x8dd83  ldstr    aUnknownCascade// "Unknown CascadeDeleteActionType enum va"...
0x8dd88  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentOutOfRangeException::.ctor(string, object, string)
0x8dd8d  throw
0x8dd8e  ldloc.s  7
0x8dd90  callvirt instance valuetype Microsoft.Crm.BusinessEntities.CascadeDeleteActionType Microsoft.Crm.BusinessEntities.CascadeRecord::get_ActionType()
0x8dd95  stloc.s  0xE
0x8dd97  ldloc.s  0xE
0x8dd99  ldc.i4.1
0x8dd9a  sub
0x8dd9b  switch   loc_8DDC1, loc_8DDC1, loc_8DDDF, loc_8DE8B
0x8ddb0  ldloc.s  0xE
0x8ddb2  ldc.i4   0xFF
0x8ddb7  beq      loc_8DED7
0x8ddbc  br       loc_8DEE8
0x8ddc1  ldloc.1
0x8ddc2  ldloc.s  7
0x8ddc4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.CascadeRecord::get_Id()
0x8ddc9  ldloc.s  7
0x8ddcb  callvirt instance int32 Microsoft.Crm.BusinessEntities.CascadeRecord::get_ObjectTypeCode()
0x8ddd0  newobj   instance void EntityKey::.ctor(valuetype [mscorlib]System.Guid objectId, int32 objectTypeCode)
0x8ddd5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype EntityKey>::Add(var<u1>)
0x8ddda  br       loc_8DF04
0x8dddf  ldloc.s  7
0x8dde1  callvirt instance int32 Microsoft.Crm.BusinessEntities.CascadeRecord::get_ObjectTypeCode()
0x8dde6  ldarg.0
0x8dde7  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass16_0::context
0x8ddec  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.BusinessEntities.CascadeEngine::GetEntityFromObjectTypeCode(int32 objectTypeCode, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x8ddf1  stloc.s  0x10
0x8ddf3  ldloc.s  0x10
0x8ddf5  ldloc.s  7
0x8ddf7  callvirt instance int32 Microsoft.Crm.BusinessEntities.CascadeRecord::get_AttributeColumnNumber()
0x8ddfc  ldloca.s 0xF
0x8ddfe  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.BusinessEntities.CascadeEngine::GetAttributeAndTypeCodeChildAttributeIfExistFromEntityAndColumnNumber(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, int32 columnNumber, [out] class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata& typeCodeChildAttribute)
0x8de03  stloc.s  0x11
0x8de05  ldloc.s  0x10
0x8de07  ldc.i4.1
0x8de08  call     class Microsoft.Crm.BusinessEntities.BusinessProcessObject Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, bool returnBaseServiceIfNoServiceFound)
0x8de0d  stloc.s  0x12
0x8de0f  ldloc.s  0x12
0x8de11  ldloc.s  0x11
0x8de13  callvirt instance bool Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteRemoveLinkUpdateForAttribute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attribute)
0x8de18  brfalse  loc_8DF04
0x8de1d  ldloc.s  0x10
0x8de1f  ldarg.0
0x8de20  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass16_0::context
0x8de25  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8de2a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, valuetype [mscorlib]System.Guid)
0x8de2f  stloc.s  0x13
0x8de31  ldloc.s  0x13
0x8de33  ldloc.s  0x10
0x8de35  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x8de3a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8de3f  ldloc.s  7
0x8de41  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.CascadeRecord::get_Id()
0x8de46  box      [mscorlib]System.Guid
0x8de4b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8de50  ldloc.s  0x13
0x8de52  ldloc.s  0x11
0x8de54  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8de59  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x8de5e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8de63  ldloc.s  0xF
0x8de65  brfalse.s loc_8DE7A
0x8de67  ldloc.s  0x13
0x8de69  ldloc.s  0xF
0x8de6b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x8de70  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x8de75  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8de7a  ldloc.s  0x12
0x8de7c  ldloc.s  0x13
0x8de7e  ldarg.0
0x8de7f  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass16_0::context
0x8de84  callvirt instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::UpdateWithPipelineAndExtensions(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8de89  br.s     loc_8DF04
0x8de8b  ldarg.0
0x8de8c  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass16_0::context
0x8de91  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8de96  ldloc.s  7
0x8de98  callvirt instance int32 Microsoft.Crm.BusinessEntities.CascadeRecord::get_ObjectTypeCode()
0x8de9d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x8dea2  ldc.i4.1
0x8dea3  call     class Microsoft.Crm.BusinessEntities.BusinessProcessObject Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata metadata, bool returnBaseServiceIfNoServiceFound)
0x8dea8  stloc.s  0x14
0x8deaa  ldloc.s  5
0x8deac  ldloc.s  0x14
0x8deae  ldloc.s  7
0x8deb0  ldarg.0
  ... truncated ...
```
