# Microsoft.Crm.ObjectModel.SavedQueryService::UpdateSearchablePropertiesOnAttributeMetadata

- ea: `0x16e460`
- end: `0x16e614`
- name: `Microsoft.Crm.ObjectModel.SavedQueryService::UpdateSearchablePropertiesOnAttributeMetadata`
- size: `436`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x16e180`
- `0x16e250`

## callees

- `0x16e440`
- `0x16e460`
- `0x16e620`
- `0x16f1b0`
- `0x16f710`

## string_xrefs

- `0x16e46c`: `fetchxml`
- `0x16e479`: `fetchxml`
- `0x16e4c0`: `fetchxml`
- `0x16e578`: `fetchxml`
- `0x16e58a`: `fetchxml`
- `0x16e5ef`: `fetchxml`

## pseudocode

```c

```

## disassembly

```asm
0x16e460  ldarg.0
0x16e461  call     instance bool Microsoft.Crm.ObjectModel.SavedQueryService::ProcessSearchMetadata()
0x16e466  brtrue.s loc_16E469
0x16e468  ret
0x16e469  ldnull
0x16e46a  stloc.0
0x16e46b  ldarg.1
0x16e46c  ldstr    aFetchxml// "fetchxml"
0x16e471  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x16e476  brtrue.s loc_16E48F
0x16e478  ldarg.1
0x16e479  ldstr    aFetchxml// "fetchxml"
0x16e47e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16e483  castclass [mscorlib]System.String
0x16e488  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x16e48d  brfalse.s loc_16E490
0x16e48f  ret
0x16e490  ldc.i4.6
0x16e491  newarr   [mscorlib]System.String
0x16e496  dup
0x16e497  ldc.i4.0
0x16e498  ldstr    aIsquickfindque// "isquickfindquery"
0x16e49d  stelem.ref
0x16e49e  dup
0x16e49f  ldc.i4.1
0x16e4a0  ldstr    aReturnedtypeco// "returnedtypecode"
0x16e4a5  stelem.ref
0x16e4a6  dup
0x16e4a7  ldc.i4.2
0x16e4a8  ldstr    aQuerytype// "querytype"
0x16e4ad  stelem.ref
0x16e4ae  dup
0x16e4af  ldc.i4.3
0x16e4b0  ldstr    aIsdefault// "isdefault"
0x16e4b5  stelem.ref
0x16e4b6  dup
0x16e4b7  ldc.i4.4
0x16e4b8  ldstr    aSolutionid// "solutionid"
0x16e4bd  stelem.ref
0x16e4be  dup
0x16e4bf  ldc.i4.5
0x16e4c0  ldstr    aFetchxml// "fetchxml"
0x16e4c5  stelem.ref
0x16e4c6  stloc.1
0x16e4c7  ldarg.0
0x16e4c8  ldarg.1
0x16e4c9  ldstr    aSavedqueryid// "savedqueryid"
0x16e4ce  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16e4d3  unbox.any [mscorlib]System.Guid
0x16e4d8  ldloc.1
0x16e4d9  ldarg.2
0x16e4da  ldarg.3
0x16e4db  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity Microsoft.Crm.ObjectModel.SavedQueryService::RetrieveSavedQueryAsUnpublished(valuetype [mscorlib]System.Guid savedQueryId, string[] columns, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache dynamicCache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x16e4e0  stloc.0
0x16e4e1  leave.s  loc_16E4E9
0x16e4e3  pop
0x16e4e4  leave    loc_16E613
0x16e4e9  ldarg.1
0x16e4ea  ldloc.0
0x16e4eb  call     bool Microsoft.Crm.ObjectModel.SavedQueryService::IsSavedQueryTypeDefaultQuickFind(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity retrievedEntity)
0x16e4f0  brtrue.s loc_16E4F3
0x16e4f2  ret
0x16e4f3  ldloc.0
0x16e4f4  ldstr    aSolutionid// "solutionid"
0x16e4f9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16e4fe  unbox.any [mscorlib]System.Guid
0x16e503  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x16e508  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x16e50d  ldarg.3
0x16e50e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x16e513  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x16e518  ldloc.0
0x16e519  ldstr    aSolutionid// "solutionid"
0x16e51e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16e523  unbox.any [mscorlib]System.Guid
0x16e528  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x16e52d  stloc.2
0x16e52e  ldloc.0
0x16e52f  ldstr    aSolutionid// "solutionid"
0x16e534  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16e539  unbox.any [mscorlib]System.Guid
0x16e53e  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x16e543  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x16e548  pop
0x16e549  ldarg.1
0x16e54a  ldstr    aReturnedtypeco// "returnedtypecode"
0x16e54f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16e554  brfalse.s loc_16E563
0x16e556  ldarg.1
0x16e557  ldstr    aReturnedtypeco// "returnedtypecode"
0x16e55c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16e561  br.s     loc_16E56E
0x16e563  ldloc.0
0x16e564  ldstr    aReturnedtypeco// "returnedtypecode"
0x16e569  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16e56e  unbox.any [mscorlib]System.Int32
0x16e573  stloc.3
0x16e574  ldloc.2
0x16e575  brtrue.s loc_16E589
0x16e577  ldloc.0
0x16e578  ldstr    aFetchxml// "fetchxml"
0x16e57d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16e582  castclass [mscorlib]System.String
0x16e587  br.s     loc_16E599
0x16e589  ldarg.1
0x16e58a  ldstr    aFetchxml// "fetchxml"
0x16e58f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16e594  castclass [mscorlib]System.String
0x16e599  stloc.s  4
0x16e59b  ldloc.2
0x16e59c  or
0x16e59d  brfalse.s loc_16E5AB
0x16e59f  ldarg.0
0x16e5a0  ldloc.3
0x16e5a1  ldloc.s  4
0x16e5a3  ldarg.3
0x16e5a4  ldc.i4.0
0x16e5a5  call     instance void Microsoft.Crm.ObjectModel.SavedQueryService::ProcessAndUpdateSearchableAttributes(int32 returnedTypeCode, string fetchxml, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool processOnlyCustomFields)
0x16e5aa  ret
0x16e5ab  ldarg.3
0x16e5ac  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x16e5b1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x16e5b6  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::SystemSolutionId
0x16e5bb  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x16e5c0  brfalse.s loc_16E613
0x16e5c2  ldloc.2
0x16e5c3  brtrue.s loc_16E613
0x16e5c5  ldloc.0
0x16e5c6  ldstr    aSolutionid// "solutionid"
0x16e5cb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16e5d0  unbox.any [mscorlib]System.Guid
0x16e5d5  stloc.s  5
0x16e5d7  ldarg.3
0x16e5d8  ldarg.3
0x16e5d9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x16e5de  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x16e5e3  ldloc.s  5
0x16e5e5  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoSolutionOperationContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext, valuetype [mscorlib]System.Guid)
0x16e5ea  stloc.s  6
0x16e5ec  ldarg.0
0x16e5ed  ldloc.3
0x16e5ee  ldloc.0
0x16e5ef  ldstr    aFetchxml// "fetchxml"
0x16e5f4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x16e5f9  castclass [mscorlib]System.String
0x16e5fe  ldarg.3
0x16e5ff  ldc.i4.0
0x16e600  call     instance void Microsoft.Crm.ObjectModel.SavedQueryService::ProcessAndUpdateSearchableAttributes(int32 returnedTypeCode, string fetchxml, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool processOnlyCustomFields)
0x16e605  leave.s  loc_16E613
0x16e607  ldloc.s  6
0x16e609  brfalse.s loc_16E612
0x16e60b  ldloc.s  6
0x16e60d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16e612  endfinally
0x16e613  ret
```
