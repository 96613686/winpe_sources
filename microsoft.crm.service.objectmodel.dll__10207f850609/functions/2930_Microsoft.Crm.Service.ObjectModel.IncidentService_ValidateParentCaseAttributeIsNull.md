# Microsoft.Crm.Service.ObjectModel.IncidentService::ValidateParentCaseAttributeIsNull

- ea: `0x2930`
- end: `0x29d6`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::ValidateParentCaseAttributeIsNull`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xfb0`

## callees

- `0x2930`

## string_xrefs

- `0x29c5`: `You can�t create child cases for child cases`

## pseudocode

```c

```

## disassembly

```asm
0x2930  ldc.i4.1
0x2931  newarr   [mscorlib]System.String
0x2936  dup
0x2937  ldc.i4.0
0x2938  ldstr    aParentcaseid// "parentcaseid"
0x293d  stelem.ref
0x293e  stloc.0
0x293f  ldarg.1
0x2940  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x2945  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x294a  ldarg.2
0x294b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x2950  stloc.1
0x2951  ldloc.1
0x2952  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2957  ldloc.0
0x2958  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x295d  ldnull
0x295e  stloc.2
0x295f  ldarg.2
0x2960  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x2965  stloc.3
0x2966  ldarg.0
0x2967  ldarg.1
0x2968  ldstr    aParentcaseid// "parentcaseid"
0x296d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x2972  unbox.any [mscorlib]System.Guid
0x2977  ldarg.1
0x2978  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x297d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x2982  ldarg.2
0x2983  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2988  ldloc.1
0x2989  ldarg.2
0x298a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x298f  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident
0x2994  stloc.2
0x2995  leave.s  loc_29A1
0x2997  ldloc.3
0x2998  brfalse.s loc_29A0
0x299a  ldloc.3
0x299b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x29a0  endfinally
0x29a1  ldloc.2
0x29a2  ldstr    aParentcaseid// "parentcaseid"
0x29a7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x29ac  brfalse.s loc_29D5
0x29ae  ldloc.2
0x29af  ldstr    aParentcaseid// "parentcaseid"
0x29b4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x29b9  callvirt instance string [mscorlib]System.Object::ToString()
0x29be  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x29c3  brtrue.s loc_29D5
0x29c5  ldstr    aYouCanTCreateC// "You can\uFFFDt create child cases for c"...
0x29ca  ldc.i4   0x8003F453
0x29cf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x29d4  throw
0x29d5  ret
```
