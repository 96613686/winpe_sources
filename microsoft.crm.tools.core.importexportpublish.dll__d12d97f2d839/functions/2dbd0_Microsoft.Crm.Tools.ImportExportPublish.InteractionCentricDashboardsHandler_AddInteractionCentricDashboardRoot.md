# Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::AddInteractionCentricDashboardRoots

- ea: `0x2dbd0`
- end: `0x2dcf9`
- name: `Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::AddInteractionCentricDashboardRoots`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x89670`

## callees

- `0x2dbd0`
- `0x2dd00`

## string_xrefs

- `0x2dc01`: `componenttype`
- `0x2dc8a`: `componenttype`
- `0x2dc17`: `rootcomponentbehavior`
- `0x2dc9d`: `rootcomponentbehavior`
- `0x2dbd0`: `SolutionComponent`

## pseudocode

```c

```

## disassembly

```asm
0x2dbd0  ldstr    aSolutioncompon// "SolutionComponent"
0x2dbd5  ldarg.1
0x2dbd6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2dbdb  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x2dbe0  stloc.0
0x2dbe1  ldarg.1
0x2dbe2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2dbe7  stloc.1
0x2dbe8  ldarg.0
0x2dbe9  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x2dbee  stloc.2
0x2dbef  br       loc_2DCD6
0x2dbf4  ldloc.2
0x2dbf5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2dbfa  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x2dbff  stloc.3
0x2dc00  ldloc.3
0x2dc01  ldstr    aComponenttype// "componenttype"
0x2dc06  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2dc0b  unbox.any [mscorlib]System.Int32
0x2dc10  ldc.i4.1
0x2dc11  bne.un   loc_2DCD6
0x2dc16  ldloc.3
0x2dc17  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x2dc1c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2dc21  unbox.any [mscorlib]System.Int32
0x2dc26  brtrue   loc_2DCD6
0x2dc2b  ldloc.1
0x2dc2c  ldloc.3
0x2dc2d  ldstr    aObjectid// "objectid"
0x2dc32  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2dc37  unbox.any [mscorlib]System.Guid
0x2dc3c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x2dc41  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x2dc46  ldarg.1
0x2dc47  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.InteractionCentricDashboardsHandler::RetrieveEntityDashboardsForExport(int32 objectTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x2dc4c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x2dc51  stloc.s  4
0x2dc53  br.s     loc_2DCB6
0x2dc55  ldloc.s  4
0x2dc57  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2dc5c  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x2dc61  stloc.s  5
0x2dc63  ldarg.1
0x2dc64  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2dc69  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent::.ctor(valuetype [mscorlib]System.Guid)
0x2dc6e  stloc.s  6
0x2dc70  ldloc.s  6
0x2dc72  ldstr    aObjectid// "objectid"
0x2dc77  ldloc.s  5
0x2dc79  ldstr    aFormid// "formid"
0x2dc7e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2dc83  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2dc88  ldloc.s  6
0x2dc8a  ldstr    aComponenttype// "componenttype"
0x2dc8f  ldc.i4.s 0x3C
0x2dc91  box      [mscorlib]System.Int32
0x2dc96  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2dc9b  ldloc.s  6
0x2dc9d  ldstr    aRootcomponentb// "rootcomponentbehavior"
0x2dca2  ldc.i4.0
0x2dca3  box      [mscorlib]System.Int32
0x2dca8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x2dcad  ldloc.0
0x2dcae  ldloc.s  6
0x2dcb0  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x2dcb5  pop
0x2dcb6  ldloc.s  4
0x2dcb8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2dcbd  brtrue.s loc_2DC55
0x2dcbf  leave.s  loc_2DCD6
0x2dcc1  ldloc.s  4
0x2dcc3  isinst   [mscorlib]System.IDisposable
0x2dcc8  stloc.s  7
0x2dcca  ldloc.s  7
0x2dccc  brfalse.s loc_2DCD5
0x2dcce  ldloc.s  7
0x2dcd0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2dcd5  endfinally
0x2dcd6  ldloc.2
0x2dcd7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2dcdc  brtrue   loc_2DBF4
0x2dce1  leave.s  loc_2DCF7
0x2dce3  ldloc.2
0x2dce4  isinst   [mscorlib]System.IDisposable
0x2dce9  stloc.s  7
0x2dceb  ldloc.s  7
0x2dced  brfalse.s loc_2DCF6
0x2dcef  ldloc.s  7
0x2dcf1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2dcf6  endfinally
0x2dcf7  ldloc.0
0x2dcf8  ret
```
