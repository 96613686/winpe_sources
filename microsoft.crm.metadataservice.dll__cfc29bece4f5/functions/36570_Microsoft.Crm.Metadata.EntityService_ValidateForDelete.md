# Microsoft.Crm.Metadata.EntityService::ValidateForDelete

- ea: `0x36570`
- end: `0x36720`
- name: `Microsoft.Crm.Metadata.EntityService::ValidateForDelete`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x31b10`

## callees

- `0x36570`

## string_xrefs

- `0x365c8`: `Cannot Delete Entity: {0}. Only Custom Entities can be deleted`
- `0x3661a`: `Cannot Delete Entity: {0}. Intersect Entities cannot be deleted`
- `0x36688`: `Cannot Delete Entity: {0}. It is used in a published workflow or used as primary entity in a draft workflow.`

## pseudocode

```c

```

## disassembly

```asm
0x36570  ldarg.2
0x36571  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x36576  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x3657b  ldarg.2
0x3657c  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x36581  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x36586  call     bool [Microsoft.Crm.Core]Microsoft.Crm.OptInSolutionHelper::IsOptInSolutionUninstall(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext)
0x3658b  brfalse.s loc_3658E
0x3658d  ret
0x3658e  ldarg.2
0x3658f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x36594  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x36599  ldarg.2
0x3659a  call     bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SolutionsHelper::IsInternalSolution(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x3659f  brtrue   loc_366B6
0x365a4  ldarg.1
0x365a5  ldstr    aIscustomentity// "iscustomentity"
0x365aa  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x365af  brtrue.s loc_365C3
0x365b1  ldarg.1
0x365b2  ldstr    aIscustomentity// "iscustomentity"
0x365b7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x365bc  unbox.any [mscorlib]System.Boolean
0x365c1  brtrue.s loc_365F6
0x365c3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x365c8  ldstr    aCannotDeleteEn// "Cannot Delete Entity: {0}. Only Custom "...
0x365cd  ldc.i4.1
0x365ce  newarr   [mscorlib]System.Object
0x365d3  dup
0x365d4  ldc.i4.0
0x365d5  ldarg.1
0x365d6  ldstr    aName// "name"
0x365db  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x365e0  castclass [mscorlib]System.String
0x365e5  stelem.ref
0x365e6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x365eb  ldc.i4   0x80047008
0x365f0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x365f5  throw
0x365f6  ldarg.1
0x365f7  ldstr    aIsintersect// "isintersect"
0x365fc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x36601  brtrue.s loc_36615
0x36603  ldarg.1
0x36604  ldstr    aIsintersect// "isintersect"
0x36609  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3660e  unbox.any [mscorlib]System.Boolean
0x36613  brfalse.s loc_36648
0x36615  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3661a  ldstr    aCannotDeleteEn_0// "Cannot Delete Entity: {0}. Intersect En"...
0x3661f  ldc.i4.1
0x36620  newarr   [mscorlib]System.Object
0x36625  dup
0x36626  ldc.i4.0
0x36627  ldarg.1
0x36628  ldstr    aName// "name"
0x3662d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x36632  castclass [mscorlib]System.String
0x36637  stelem.ref
0x36638  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3663d  ldc.i4   0x8004830F
0x36642  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x36647  throw
0x36648  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowService::.ctor()
0x3664d  stloc.0
0x3664e  ldc.i4.1
0x3664f  newarr   [mscorlib]System.Int32
0x36654  dup
0x36655  ldc.i4.0
0x36656  ldc.i4.2
0x36657  stelem.i4
0x36658  stloc.1
0x36659  ldloc.0
0x3665a  ldarg.1
0x3665b  ldstr    aLogicalname// "logicalname"
0x36660  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x36665  castclass [mscorlib]System.String
0x3666a  ldarg.1
0x3666b  ldstr    aObjecttypecode_0// "objecttypecode"
0x36670  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x36675  unbox.any [mscorlib]System.Int32
0x3667a  ldloc.1
0x3667b  ldarg.2
0x3667c  callvirt instance bool class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.WorkflowServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.UpgradingOff>::IsEntityUsedInWorkflows(string, int32, int32[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x36681  brfalse.s loc_366B6
0x36683  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x36688  ldstr    aCannotDeleteEn_1// "Cannot Delete Entity: {0}. It is used i"...
0x3668d  ldc.i4.1
0x3668e  newarr   [mscorlib]System.Object
0x36693  dup
0x36694  ldc.i4.0
0x36695  ldarg.1
0x36696  ldstr    aName// "name"
0x3669b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x366a0  castclass [mscorlib]System.String
0x366a5  stelem.ref
0x366a6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x366ab  ldc.i4   0x8004502C
0x366b0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x366b5  throw
0x366b6  ldarg.2
0x366b7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x366bc  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionOperationContext()
0x366c1  ldc.i4.2
0x366c2  beq.s    loc_3671F
0x366c4  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyProcessor::.ctor()
0x366c9  ldarg.1
0x366ca  ldstr    aEntityid// "entityid"
0x366cf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x366d4  unbox.any [mscorlib]System.Guid
0x366d9  ldc.i4.1
0x366da  ldarg.2
0x366db  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.DependencyProcessor::RetrieveDependenciesForDelete(valuetype [mscorlib]System.Guid, int32, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x366e0  stloc.2
0x366e1  ldloc.2
0x366e2  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x366e7  ldc.i4.0
0x366e8  ble.s    loc_3671F
0x366ea  ldc.i4   0x8004F01F
0x366ef  ldc.i4.3
0x366f0  newarr   [mscorlib]System.Object
0x366f5  dup
0x366f6  ldc.i4.0
0x366f7  ldstr    aEntity_0// "Entity"
0x366fc  stelem.ref
0x366fd  dup
0x366fe  ldc.i4.1
0x366ff  ldarg.1
0x36700  ldstr    aEntityid// "entityid"
0x36705  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3670a  stelem.ref
0x3670b  dup
0x3670c  ldc.i4.2
0x3670d  ldloc.2
0x3670e  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x36713  box      [mscorlib]System.Int32
0x36718  stelem.ref
0x36719  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x3671e  throw
0x3671f  ret
```
