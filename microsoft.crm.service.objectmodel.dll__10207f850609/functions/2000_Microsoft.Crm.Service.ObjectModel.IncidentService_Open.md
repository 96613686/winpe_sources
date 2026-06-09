# Microsoft.Crm.Service.ObjectModel.IncidentService::Open

- ea: `0x2000`
- end: `0x20c3`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::Open`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1740`

## callees

- `0x2000`
- `0x20e0`
- `0x2200`

## pseudocode

```c

```

## disassembly

```asm
0x2000  ldc.i4.3
0x2001  newarr   [mscorlib]System.String
0x2006  dup
0x2007  ldc.i4.0
0x2008  ldstr    aStatecode// "statecode"
0x200d  stelem.ref
0x200e  dup
0x200f  ldc.i4.1
0x2010  ldstr    aStatuscode// "statuscode"
0x2015  stelem.ref
0x2016  dup
0x2017  ldc.i4.2
0x2018  ldstr    aOwnerid// "ownerid"
0x201d  stelem.ref
0x201e  stloc.0
0x201f  ldarg.3
0x2020  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x2025  newobj   instance void [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident::.ctor(valuetype [mscorlib]System.Guid)
0x202a  stloc.1
0x202b  ldloc.1
0x202c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x2031  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x2036  ldarg.3
0x2037  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x203c  stloc.2
0x203d  ldloc.2
0x203e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2043  ldloc.0
0x2044  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x2049  ldarg.3
0x204a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x204f  stloc.s  4
0x2051  ldarg.0
0x2052  ldarg.1
0x2053  ldloc.2
0x2054  ldarg.3
0x2055  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x205a  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.Incident
0x205f  stloc.1
0x2060  leave.s  loc_206E
0x2062  ldloc.s  4
0x2064  brfalse.s loc_206D
0x2066  ldloc.s  4
0x2068  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x206d  endfinally
0x206e  ldloc.1
0x206f  ldstr    aStatecode// "statecode"
0x2074  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2079  unbox.any [mscorlib]System.Int32
0x207e  stloc.3
0x207f  ldloc.1
0x2080  ldstr    aOwnerid// "ownerid"
0x2085  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x208a  unbox.any [mscorlib]System.Guid
0x208f  pop
0x2090  ldloc.3
0x2091  brtrue.s loc_20A8
0x2093  ldarg.2
0x2094  ldloc.1
0x2095  ldstr    aStatuscode// "statuscode"
0x209a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x209f  unbox.any [mscorlib]System.Int32
0x20a4  bne.un.s loc_20A8
0x20a6  ldc.i4.0
0x20a7  ret
0x20a8  ldloc.3
0x20a9  brfalse.s loc_20B8
0x20ab  ldarg.0
0x20ac  ldarg.1
0x20ad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x20b2  ldarg.3
0x20b3  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::CancelIncidentResolutionActivity(valuetype [mscorlib]System.Guid incidentId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x20b8  ldarg.0
0x20b9  ldarg.1
0x20ba  ldc.i4.0
0x20bb  ldarg.2
0x20bc  ldarg.3
0x20bd  call     instance bool Microsoft.Crm.Service.ObjectModel.IncidentService::SetStateInternal(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, int32 newState, int32 newStatusCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x20c2  ret
```
