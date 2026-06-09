# Microsoft.Crm.Service.ObjectModel.ContractStateAsyncJobHelper::UpdateAsyncJobPostponeUntil

- ea: `0x4740`
- end: `0x4926`
- name: `Microsoft.Crm.Service.ObjectModel.ContractStateAsyncJobHelper::UpdateAsyncJobPostponeUntil`
- size: `486`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3160`
- `0x36c0`
- `0x3710`

## callees

- `0x4740`

## pseudocode

```c

```

## disassembly

```asm
0x4740  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x4745  brfalse.s loc_4748
0x4747  ret
0x4748  ldloca.s 0
0x474a  ldstr    a5eb14ecb60ed4f// "5eb14ecb-60ed-4f59-800d-a6c09455c9d8"
0x474f  call     instance void [mscorlib]System.Guid::.ctor(string)
0x4754  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4759  stloc.1
0x475a  ldarg.0
0x475b  ldc.i4.0
0x475c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x4761  stloc.2
0x4762  ldarg.0
0x4763  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4768  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AsyncOperation::.ctor(valuetype [mscorlib]System.Guid)
0x476d  stloc.3
0x476e  ldloc.3
0x476f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x4774  ldarg.0
0x4775  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x477a  stloc.s  4
0x477c  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncOperationService::.ctor()
0x4781  stloc.s  5
0x4783  ldloc.s  4
0x4785  ldc.i4.1
0x4786  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_NoLock(bool)
0x478b  ldloc.s  4
0x478d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x4792  ldc.i4.2
0x4793  newarr   [mscorlib]System.String
0x4798  dup
0x4799  ldc.i4.0
0x479a  ldstr    aRecurrencestar// "recurrencestarttime"
0x479f  stelem.ref
0x47a0  dup
0x47a1  ldc.i4.1
0x47a2  ldstr    aPostponeuntil// "postponeuntil"
0x47a7  stelem.ref
0x47a8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x47ad  ldloc.0
0x47ae  ldloc.3
0x47af  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x47b4  ldarg.0
0x47b5  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x47ba  stloc.s  6
0x47bc  ldloc.s  5
0x47be  ldloc.s  6
0x47c0  ldloc.s  4
0x47c2  ldarg.0
0x47c3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x47c8  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AsyncOperation
0x47cd  stloc.3
0x47ce  ldloc.3
0x47cf  brtrue.s loc_4804
0x47d1  ldnull
0x47d2  ldarg.0
0x47d3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x47d8  ldc.i4.s 0x15
0x47da  ldstr    aRecurringAsync// " Recurring Async job {0} for Contracts "...
0x47df  ldc.i4.1
0x47e0  newarr   [mscorlib]System.Object
0x47e5  dup
0x47e6  ldc.i4.0
0x47e7  ldloc.0
0x47e8  box      [mscorlib]System.Guid
0x47ed  stelem.ref
0x47ee  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x47f3  ldc.i4   0x80044164
0x47f8  ldc.i4.0
0x47f9  newarr   [mscorlib]System.Object
0x47fe  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x4803  throw
0x4804  ldloca.s 1
0x4806  ldc.r8   1.0
0x480f  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x4814  stloc.s  7
0x4816  ldloca.s 1
0x4818  ldc.r8   1.0
0x4821  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x4826  stloc.s  8
0x4828  ldloc.3
0x4829  ldstr    aPostponeuntil// "postponeuntil"
0x482e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x4833  brtrue.s loc_484C
0x4835  ldloc.3
0x4836  ldstr    aPostponeuntil// "postponeuntil"
0x483b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4840  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x4845  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x484a  stloc.s  7
0x484c  ldloc.3
0x484d  ldstr    aRecurrencestar// "recurrencestarttime"
0x4852  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x4857  brtrue.s loc_4870
0x4859  ldloc.3
0x485a  ldstr    aRecurrencestar// "recurrencestarttime"
0x485f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4864  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x4869  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x486e  stloc.s  8
0x4870  ldloc.s  7
0x4872  ldloca.s 1
0x4874  ldc.r8   1.0
0x487d  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x4882  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x4887  brfalse.s loc_488E
0x4889  leave    loc_4925
0x488e  ldloca.s 9
0x4890  ldloca.s 1
0x4892  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x4897  ldloca.s 1
0x4899  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x489e  ldloca.s 1
0x48a0  call     instance int32 [mscorlib]System.DateTime::get_Day()
0x48a5  ldloca.s 8
0x48a7  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0x48ac  ldloca.s 8
0x48ae  call     instance int32 [mscorlib]System.DateTime::get_Minute()
0x48b3  ldloca.s 8
0x48b5  call     instance int32 [mscorlib]System.DateTime::get_Second()
0x48ba  ldc.i4.1
0x48bb  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32, valuetype [mscorlib]System.DateTimeKind)
0x48c0  ldloc.s  9
0x48c2  ldloc.1
0x48c3  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x48c8  brfalse.s loc_48DC
0x48ca  ldloca.s 9
0x48cc  ldc.r8   1.0
0x48d5  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x48da  stloc.s  9
0x48dc  ldarg.0
0x48dd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x48e2  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AsyncOperation::.ctor(valuetype [mscorlib]System.Guid)
0x48e7  stloc.s  0xA
0x48e9  ldloc.s  0xA
0x48eb  ldstr    aPostponeuntil// "postponeuntil"
0x48f0  ldloc.s  9
0x48f2  ldc.i4.1
0x48f3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x48f8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x48fd  ldloc.s  0xA
0x48ff  ldstr    aAsyncoperation// "asyncoperationid"
0x4904  ldloc.3
0x4905  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x490a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x490f  ldloc.s  5
0x4911  ldloc.s  0xA
0x4913  ldarg.0
0x4914  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4919  leave.s  loc_4925
0x491b  ldloc.2
0x491c  brfalse.s loc_4924
0x491e  ldloc.2
0x491f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4924  endfinally
0x4925  ret
```
