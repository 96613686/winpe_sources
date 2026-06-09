# Microsoft.Crm.Service.ObjectModel.IncidentService::Cancel

- ea: `0x2160`
- end: `0x21fc`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::Cancel`
- size: `156`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1740`
- `0x1da0`

## callees

- `0x2160`
- `0x2200`
- `0x2360`

## pseudocode

```c

```

## disassembly

```asm
0x2160  ldc.i4.1
0x2161  newarr   [mscorlib]System.String
0x2166  dup
0x2167  ldc.i4.0
0x2168  ldstr    aStatecode// "statecode"
0x216d  stelem.ref
0x216e  stloc.0
0x216f  ldarg.3
0x2170  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2175  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident::.ctor(valuetype [mscorlib]System.Guid)
0x217a  stloc.1
0x217b  ldloc.1
0x217c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x2181  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x2186  ldarg.3
0x2187  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x218c  stloc.2
0x218d  ldloc.2
0x218e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2193  ldloc.0
0x2194  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x2199  ldarg.3
0x219a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x219f  stloc.s  4
0x21a1  ldarg.0
0x21a2  ldarg.1
0x21a3  ldloc.2
0x21a4  ldarg.3
0x21a5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x21aa  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident
0x21af  stloc.1
0x21b0  leave.s  loc_21BE
0x21b2  ldloc.s  4
0x21b4  brfalse.s loc_21BD
0x21b6  ldloc.s  4
0x21b8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21bd  endfinally
0x21be  ldloc.1
0x21bf  ldstr    aStatecode// "statecode"
0x21c4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x21c9  unbox.any [mscorlib]System.Int32
0x21ce  stloc.3
0x21cf  ldloc.3
0x21d0  ldc.i4.1
0x21d1  beq.s    loc_21D7
0x21d3  ldloc.3
0x21d4  ldc.i4.2
0x21d5  bne.un.s loc_21E8
0x21d7  ldc.i4   0x80044411
0x21dc  ldc.i4.0
0x21dd  newarr   [mscorlib]System.Object
0x21e2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x21e7  throw
0x21e8  ldarg.0
0x21e9  ldloc.1
0x21ea  ldarg.3
0x21eb  ldc.i4.2
0x21ec  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::ChangeActivitiesStatus(class [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident incident, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, int32 newState)
0x21f1  ldarg.0
0x21f2  ldarg.1
0x21f3  ldc.i4.2
0x21f4  ldarg.2
0x21f5  ldarg.3
0x21f6  call     instance bool Microsoft.Crm.Service.ObjectModel.IncidentService::SetStateInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, int32 newState, int32 newStatusCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x21fb  ret
```
