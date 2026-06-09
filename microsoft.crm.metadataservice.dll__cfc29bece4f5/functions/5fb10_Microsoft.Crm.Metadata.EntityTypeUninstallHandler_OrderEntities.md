# Microsoft.Crm.Metadata.EntityTypeUninstallHandler::OrderEntities

- ea: `0x5fb10`
- end: `0x5fdd3`
- name: `Microsoft.Crm.Metadata.EntityTypeUninstallHandler::OrderEntities`
- size: `707`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5faa0`

## callees

- `0x5fb10`
- `0x5fde0`

## string_xrefs

- `0x5fb10`: `SolutionComponent`

## pseudocode

```c

```

## disassembly

```asm
0x5fb10  ldstr    aSolutioncompon// "SolutionComponent"
0x5fb15  ldarg.2
0x5fb16  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x5fb1b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5fb20  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x5fb25  stloc.0
0x5fb26  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x5fb2b  stloc.1
0x5fb2c  ldarg.1
0x5fb2d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5fb32  stloc.2
0x5fb33  br       loc_5FBD0
0x5fb38  ldloc.2
0x5fb39  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5fb3e  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5fb43  stloc.3
0x5fb44  ldloc.3
0x5fb45  ldstr    aObjectid// "objectid"
0x5fb4a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5fb4f  unbox.any [mscorlib]System.Guid
0x5fb54  stloc.s  4
0x5fb56  ldarg.2
0x5fb57  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_Cache()
0x5fb5c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Entities()
0x5fb61  ldloc.s  4
0x5fb63  box      [mscorlib]System.Guid
0x5fb68  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Item(!!T0)
0x5fb6d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsIntersect()
0x5fb72  brtrue.s loc_5FBD0
0x5fb74  ldarg.2
0x5fb75  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_Cache()
0x5fb7a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Entities()
0x5fb7f  ldloc.s  4
0x5fb81  box      [mscorlib]System.Guid
0x5fb86  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Item(!!T0)
0x5fb8b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x5fb90  brtrue.s loc_5FBD0
0x5fb92  ldarg.2
0x5fb93  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_Cache()
0x5fb98  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Entities()
0x5fb9d  ldloc.s  4
0x5fb9f  box      [mscorlib]System.Guid
0x5fba4  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Item(!!T0)
0x5fba9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x5fbae  brtrue.s loc_5FBBF
0x5fbb0  ldloc.s  4
0x5fbb2  ldarg.2
0x5fbb3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x5fbb8  call     bool Microsoft.Crm.Metadata.EntityTypeUninstallHandler::IsFirstPartySystemEntity(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5fbbd  brfalse.s loc_5FBD0
0x5fbbf  ldloc.0
0x5fbc0  ldloc.3
0x5fbc1  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x5fbc6  pop
0x5fbc7  ldloc.1
0x5fbc8  ldloc.s  4
0x5fbca  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x5fbcf  pop
0x5fbd0  ldloc.2
0x5fbd1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5fbd6  brtrue   loc_5FB38
0x5fbdb  leave.s  loc_5FBF1
0x5fbdd  ldloc.2
0x5fbde  isinst   [mscorlib]System.IDisposable
0x5fbe3  stloc.s  5
0x5fbe5  ldloc.s  5
0x5fbe7  brfalse.s loc_5FBF0
0x5fbe9  ldloc.s  5
0x5fbeb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5fbf0  endfinally
0x5fbf1  ldarg.1
0x5fbf2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5fbf7  stloc.2
0x5fbf8  br       loc_5FC84
0x5fbfd  ldloc.2
0x5fbfe  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5fc03  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5fc08  stloc.s  6
0x5fc0a  ldloc.s  6
0x5fc0c  ldstr    aObjectid// "objectid"
0x5fc11  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5fc16  unbox.any [mscorlib]System.Guid
0x5fc1b  stloc.s  7
0x5fc1d  ldloc.1
0x5fc1e  ldloc.s  7
0x5fc20  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x5fc25  brtrue.s loc_5FC84
0x5fc27  ldarg.2
0x5fc28  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_Cache()
0x5fc2d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Entities()
0x5fc32  ldloc.s  7
0x5fc34  box      [mscorlib]System.Guid
0x5fc39  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Item(!!T0)
0x5fc3e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x5fc43  brfalse.s loc_5FC84
0x5fc45  ldarg.2
0x5fc46  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_Cache()
0x5fc4b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Entities()
0x5fc50  ldloc.s  7
0x5fc52  box      [mscorlib]System.Guid
0x5fc57  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Item(!!T0)
0x5fc5c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x5fc61  brtrue.s loc_5FC72
0x5fc63  ldloc.s  7
0x5fc65  ldarg.2
0x5fc66  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x5fc6b  call     bool Microsoft.Crm.Metadata.EntityTypeUninstallHandler::IsFirstPartySystemEntity(valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5fc70  brfalse.s loc_5FC84
0x5fc72  ldloc.0
0x5fc73  ldloc.s  6
0x5fc75  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x5fc7a  pop
0x5fc7b  ldloc.1
0x5fc7c  ldloc.s  7
0x5fc7e  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x5fc83  pop
0x5fc84  ldloc.2
0x5fc85  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5fc8a  brtrue   loc_5FBFD
0x5fc8f  leave.s  loc_5FCA5
0x5fc91  ldloc.2
0x5fc92  isinst   [mscorlib]System.IDisposable
0x5fc97  stloc.s  5
0x5fc99  ldloc.s  5
0x5fc9b  brfalse.s loc_5FCA4
0x5fc9d  ldloc.s  5
0x5fc9f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5fca4  endfinally
0x5fca5  ldarg.1
0x5fca6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5fcab  stloc.2
0x5fcac  br.s     loc_5FD26
0x5fcae  ldloc.2
0x5fcaf  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5fcb4  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5fcb9  stloc.s  8
0x5fcbb  ldloc.s  8
0x5fcbd  ldstr    aObjectid// "objectid"
0x5fcc2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5fcc7  unbox.any [mscorlib]System.Guid
0x5fccc  stloc.s  9
0x5fcce  ldloc.1
0x5fccf  ldloc.s  9
0x5fcd1  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x5fcd6  brtrue.s loc_5FD26
0x5fcd8  ldarg.2
0x5fcd9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_Cache()
0x5fcde  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Entities()
0x5fce3  ldloc.s  9
0x5fce5  box      [mscorlib]System.Guid
0x5fcea  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Item(!!T0)
0x5fcef  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsIntersect()
0x5fcf4  brtrue.s loc_5FD26
0x5fcf6  ldarg.2
0x5fcf7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_Cache()
0x5fcfc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Entities()
0x5fd01  ldloc.s  9
0x5fd03  box      [mscorlib]System.Guid
0x5fd08  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Item(!!T0)
0x5fd0d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x5fd12  brtrue.s loc_5FD26
0x5fd14  ldloc.0
0x5fd15  ldloc.s  8
0x5fd17  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x5fd1c  pop
0x5fd1d  ldloc.1
0x5fd1e  ldloc.s  9
0x5fd20  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x5fd25  pop
0x5fd26  ldloc.2
0x5fd27  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5fd2c  brtrue.s loc_5FCAE
0x5fd2e  leave.s  loc_5FD44
0x5fd30  ldloc.2
0x5fd31  isinst   [mscorlib]System.IDisposable
0x5fd36  stloc.s  5
0x5fd38  ldloc.s  5
0x5fd3a  brfalse.s loc_5FD43
0x5fd3c  ldloc.s  5
0x5fd3e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5fd43  endfinally
0x5fd44  ldarg.2
0x5fd45  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_SolutionId()
0x5fd4a  ldarg.2
0x5fd4b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_ExecutionContext()
0x5fd50  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SolutionsHelper::IsInternalSolution(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5fd55  brtrue.s loc_5FD59
0x5fd57  ldloc.0
0x5fd58  ret
0x5fd59  ldarg.1
0x5fd5a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5fd5f  stloc.2
0x5fd60  br.s     loc_5FDB3
0x5fd62  ldloc.2
0x5fd63  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5fd68  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5fd6d  stloc.s  0xA
0x5fd6f  ldloc.s  0xA
0x5fd71  ldstr    aObjectid// "objectid"
0x5fd76  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5fd7b  unbox.any [mscorlib]System.Guid
0x5fd80  stloc.s  0xB
0x5fd82  ldloc.1
0x5fd83  ldloc.s  0xB
0x5fd85  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::Contains(var<u1>)
0x5fd8a  brtrue.s loc_5FDB3
0x5fd8c  ldarg.2
0x5fd8d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionUninstallContext::get_Cache()
0x5fd92  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Entities()
0x5fd97  ldloc.s  0xB
0x5fd99  box      [mscorlib]System.Guid
0x5fd9e  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Item(!!T0)
0x5fda3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsIntersect()
0x5fda8  brfalse.s loc_5FDB3
0x5fdaa  ldloc.0
0x5fdab  ldloc.s  0xA
0x5fdad  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x5fdb2  pop
0x5fdb3  ldloc.2
0x5fdb4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5fdb9  brtrue.s loc_5FD62
0x5fdbb  leave.s  loc_5FDD1
0x5fdbd  ldloc.2
0x5fdbe  isinst   [mscorlib]System.IDisposable
0x5fdc3  stloc.s  5
0x5fdc5  ldloc.s  5
0x5fdc7  brfalse.s loc_5FDD0
0x5fdc9  ldloc.s  5
0x5fdcb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5fdd0  endfinally
0x5fdd1  ldloc.0
0x5fdd2  ret
```
