# Microsoft.Crm.ObjectModel.SharePointDocumentLocationServiceInternal`1::MergeUpdate

- ea: `0x17b5c0`
- end: `0x17b6af`
- name: `Microsoft.Crm.ObjectModel.SharePointDocumentLocationServiceInternal`1::MergeUpdate`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x17b5c0`

## string_xrefs

- `0x17b5dc`: `servicetype`
- `0x17b5ee`: `servicetype`
- `0x17b618`: `servicetype`
- `0x17b625`: `servicetype`
- `0x17b642`: `servicetype`
- `0x17b65f`: `servicetype`
- `0x17b66c`: `servicetype`
- `0x17b689`: `servicetype`

## pseudocode

```c

```

## disassembly

```asm
0x17b5c0  ldstr    aSharepointdocu_4// "SharePointDocumentLocation"
0x17b5c5  ldarg.2
0x17b5c6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x17b5cb  stloc.0
0x17b5cc  ldloc.0
0x17b5cd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x17b5d2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::get_EntityMetadata()
0x17b5d7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x17b5dc  ldstr    aServicetype// "servicetype"
0x17b5e1  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x17b5e6  brfalse.s loc_17B5F8
0x17b5e8  ldloc.0
0x17b5e9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x17b5ee  ldstr    aServicetype// "servicetype"
0x17b5f3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x17b5f8  ldarg.0
0x17b5f9  ldarg.1
0x17b5fa  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x17b5ff  unbox.any [mscorlib]System.Guid
0x17b604  ldstr    aSharepointdocu_4// "SharePointDocumentLocation"
0x17b609  ldarg.2
0x17b60a  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17b60f  ldloc.0
0x17b610  ldarg.2
0x17b611  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x17b616  stloc.1
0x17b617  ldarg.1
0x17b618  ldstr    aServicetype// "servicetype"
0x17b61d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x17b622  brtrue.s loc_17B65E
0x17b624  ldarg.1
0x17b625  ldstr    aServicetype// "servicetype"
0x17b62a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x17b62f  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17b634  ldc.i4.1
0x17b635  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17b63a  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17b63f  beq.s    loc_17B6A5
0x17b641  ldarg.1
0x17b642  ldstr    aServicetype// "servicetype"
0x17b647  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x17b64c  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17b651  ldc.i4.2
0x17b652  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17b657  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17b65c  beq.s    loc_17B6A5
0x17b65e  ldloc.1
0x17b65f  ldstr    aServicetype// "servicetype"
0x17b664  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x17b669  brtrue.s loc_17B6A6
0x17b66b  ldloc.1
0x17b66c  ldstr    aServicetype// "servicetype"
0x17b671  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x17b676  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17b67b  ldc.i4.1
0x17b67c  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17b681  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17b686  beq.s    loc_17B6A5
0x17b688  ldloc.1
0x17b689  ldstr    aServicetype// "servicetype"
0x17b68e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x17b693  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17b698  ldc.i4.2
0x17b699  box      [Microsoft.Crm]Microsoft.Crm.SharePointSiteType
0x17b69e  call     int32 [mscorlib]System.Convert::ToInt32(object)
0x17b6a3  bne.un.s loc_17B6A6
0x17b6a5  ret
0x17b6a6  ldarg.0
0x17b6a7  ldarg.1
0x17b6a8  ldarg.2
0x17b6a9  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::MergeUpdate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x17b6ae  ret
```
