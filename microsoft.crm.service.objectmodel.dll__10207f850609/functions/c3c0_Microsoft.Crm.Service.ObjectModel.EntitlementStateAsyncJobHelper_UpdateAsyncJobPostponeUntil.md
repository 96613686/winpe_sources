# Microsoft.Crm.Service.ObjectModel.EntitlementStateAsyncJobHelper::UpdateAsyncJobPostponeUntil

- ea: `0xc3c0`
- end: `0xc5a5`
- name: `Microsoft.Crm.Service.ObjectModel.EntitlementStateAsyncJobHelper::UpdateAsyncJobPostponeUntil`
- size: `485`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xb500`
- `0xb5d0`

## callees

- `0xc3c0`

## pseudocode

```c

```

## disassembly

```asm
0xc3c0  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0xc3c5  brfalse.s loc_C3C8
0xc3c7  ret
0xc3c8  ldloca.s 0
0xc3ca  ldstr    a46eb574aD4e04b// "46EB574A-D4E0-4BE1-96EA-731B9D5BAF3A"
0xc3cf  call     instance void [mscorlib]System.Guid::.ctor(string)
0xc3d4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xc3d9  stloc.1
0xc3da  ldarg.0
0xc3db  ldc.i4.0
0xc3dc  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0xc3e1  stloc.2
0xc3e2  ldarg.0
0xc3e3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xc3e8  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AsyncOperation::.ctor(valuetype [mscorlib]System.Guid)
0xc3ed  stloc.3
0xc3ee  ldloc.3
0xc3ef  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0xc3f4  ldarg.0
0xc3f5  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xc3fa  stloc.s  4
0xc3fc  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncOperationService::.ctor()
0xc401  stloc.s  5
0xc403  ldloc.s  4
0xc405  ldc.i4.1
0xc406  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_NoLock(bool)
0xc40b  ldloc.s  4
0xc40d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xc412  ldc.i4.2
0xc413  newarr   [mscorlib]System.String
0xc418  dup
0xc419  ldc.i4.0
0xc41a  ldstr    aRecurrencestar// "recurrencestarttime"
0xc41f  stelem.ref
0xc420  dup
0xc421  ldc.i4.1
0xc422  ldstr    aPostponeuntil// "postponeuntil"
0xc427  stelem.ref
0xc428  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xc42d  ldloc.0
0xc42e  ldloc.3
0xc42f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0xc434  ldarg.0
0xc435  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc43a  stloc.s  6
0xc43c  ldloc.s  5
0xc43e  ldloc.s  6
0xc440  ldloc.s  4
0xc442  ldarg.0
0xc443  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xc448  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AsyncOperation
0xc44d  stloc.3
0xc44e  ldloc.3
0xc44f  brtrue.s loc_C483
0xc451  ldnull
0xc452  ldarg.0
0xc453  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xc458  ldc.i4.s 0x15
0xc45a  ldstr    aRecurringAsync_0// " Recurring Async job {0} for Entitlemen"...
0xc45f  ldc.i4.1
0xc460  newarr   [mscorlib]System.Object
0xc465  dup
0xc466  ldc.i4.0
0xc467  ldloc.0
0xc468  box      [mscorlib]System.Guid
0xc46d  stelem.ref
0xc46e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xc473  ldstr    aAsyncJobForEnt// "Async Job for Entitlement updation not "...
0xc478  ldc.i4   0x80044164
0xc47d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xc482  throw
0xc483  ldloca.s 1
0xc485  ldc.r8   1.0
0xc48e  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xc493  stloc.s  7
0xc495  ldloca.s 1
0xc497  ldc.r8   1.0
0xc4a0  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xc4a5  stloc.s  8
0xc4a7  ldloc.3
0xc4a8  ldstr    aPostponeuntil// "postponeuntil"
0xc4ad  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0xc4b2  brtrue.s loc_C4CB
0xc4b4  ldloc.3
0xc4b5  ldstr    aPostponeuntil// "postponeuntil"
0xc4ba  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xc4bf  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0xc4c4  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0xc4c9  stloc.s  7
0xc4cb  ldloc.3
0xc4cc  ldstr    aRecurrencestar// "recurrencestarttime"
0xc4d1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0xc4d6  brtrue.s loc_C4EF
0xc4d8  ldloc.3
0xc4d9  ldstr    aRecurrencestar// "recurrencestarttime"
0xc4de  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xc4e3  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0xc4e8  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0xc4ed  stloc.s  8
0xc4ef  ldloc.s  7
0xc4f1  ldloca.s 1
0xc4f3  ldc.r8   1.0
0xc4fc  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xc501  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xc506  brfalse.s loc_C50D
0xc508  leave    loc_C5A4
0xc50d  ldloca.s 9
0xc50f  ldloca.s 1
0xc511  call     instance int32 [mscorlib]System.DateTime::get_Year()
0xc516  ldloca.s 1
0xc518  call     instance int32 [mscorlib]System.DateTime::get_Month()
0xc51d  ldloca.s 1
0xc51f  call     instance int32 [mscorlib]System.DateTime::get_Day()
0xc524  ldloca.s 8
0xc526  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0xc52b  ldloca.s 8
0xc52d  call     instance int32 [mscorlib]System.DateTime::get_Minute()
0xc532  ldloca.s 8
0xc534  call     instance int32 [mscorlib]System.DateTime::get_Second()
0xc539  ldc.i4.1
0xc53a  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32, valuetype [mscorlib]System.DateTimeKind)
0xc53f  ldloc.s  9
0xc541  ldloc.1
0xc542  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xc547  brfalse.s loc_C55B
0xc549  ldloca.s 9
0xc54b  ldc.r8   1.0
0xc554  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xc559  stloc.s  9
0xc55b  ldarg.0
0xc55c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xc561  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AsyncOperation::.ctor(valuetype [mscorlib]System.Guid)
0xc566  stloc.s  0xA
0xc568  ldloc.s  0xA
0xc56a  ldstr    aPostponeuntil// "postponeuntil"
0xc56f  ldloc.s  9
0xc571  ldc.i4.1
0xc572  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0xc577  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xc57c  ldloc.s  0xA
0xc57e  ldstr    aAsyncoperation// "asyncoperationid"
0xc583  ldloc.3
0xc584  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0xc589  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0xc58e  ldloc.s  5
0xc590  ldloc.s  0xA
0xc592  ldarg.0
0xc593  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xc598  leave.s  loc_C5A4
0xc59a  ldloc.2
0xc59b  brfalse.s loc_C5A3
0xc59d  ldloc.2
0xc59e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc5a3  endfinally
0xc5a4  ret
```
