# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleHelper::RescheduleKnowledgeArticleAsyncJob

- ea: `0xff10`
- end: `0x100f7`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleHelper::RescheduleKnowledgeArticleAsyncJob`
- size: `487`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xd1c0`
- `0xd3e0`

## callees

- `0xff00`
- `0xff10`

## string_xrefs

- `0x1008f`: `Knowledge Article Asyncjob rescheduled from {0} to {1} `

## pseudocode

```c

```

## disassembly

```asm
0xff10  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0xff15  brtrue   loc_100F6
0xff1a  ldarg.0
0xff1b  ldc.i4.0
0xff1c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0xff21  stloc.0
0xff22  ldarg.0
0xff23  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xff28  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AsyncOperation::.ctor(valuetype [mscorlib]System.Guid)
0xff2d  stloc.1
0xff2e  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncOperationService::.ctor()
0xff33  stloc.2
0xff34  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xff39  stloc.3
0xff3a  ldloc.1
0xff3b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0xff40  ldarg.0
0xff41  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xff46  stloc.s  4
0xff48  ldloc.s  4
0xff4a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xff4f  ldstr    aPostponeuntil// "postponeuntil"
0xff54  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0xff59  ldloc.s  4
0xff5b  ldc.i4.1
0xff5c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_NoLock(bool)
0xff61  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Service.ObjectModel.KnowledgeArticleHelper::GetKnowledgeArticleAsyncJobId()
0xff66  ldloc.1
0xff67  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0xff6c  ldarg.0
0xff6d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xff72  stloc.s  5
0xff74  ldloc.2
0xff75  ldloc.s  5
0xff77  ldloc.s  4
0xff79  ldarg.0
0xff7a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xff7f  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AsyncOperation
0xff84  stloc.1
0xff85  ldloc.1
0xff86  brfalse  loc_100B4
0xff8b  ldloca.s 3
0xff8d  ldc.r8   1.0
0xff96  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xff9b  stloc.s  6
0xff9d  ldloc.1
0xff9e  ldstr    aPostponeuntil// "postponeuntil"
0xffa3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0xffa8  brtrue.s loc_FFC1
0xffaa  ldloc.1
0xffab  ldstr    aPostponeuntil// "postponeuntil"
0xffb0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xffb5  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0xffba  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0xffbf  stloc.s  6
0xffc1  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xffc6  stloc.s  8
0xffc8  ldloca.s 8
0xffca  ldc.r8   1.0
0xffd3  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0xffd8  stloc.s  7
0xffda  ldarg.1
0xffdb  brfalse.s loc_FFFC
0xffdd  ldarg.1
0xffde  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0xffe3  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0xffe8  brfalse.s loc_FFFC
0xffea  ldarg.1
0xffeb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0xfff0  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0xfff5  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0xfffa  stloc.s  7
0xfffc  ldarg.2
0xfffd  brfalse.s loc_10031
0xffff  ldarg.2
0x10000  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x10005  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x1000a  brfalse.s loc_10031
0x1000c  ldarg.2
0x1000d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x10012  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x10017  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x1001c  stloc.s  9
0x1001e  ldloc.s  9
0x10020  ldloc.s  7
0x10022  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x10027  brtrue.s loc_1002D
0x10029  ldloc.s  7
0x1002b  br.s     loc_1002F
0x1002d  ldloc.s  9
0x1002f  stloc.s  7
0x10031  ldloc.s  7
0x10033  ldloc.s  6
0x10035  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1003a  brfalse  loc_100EA
0x1003f  ldarg.0
0x10040  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x10045  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AsyncOperation::.ctor(valuetype [mscorlib]System.Guid)
0x1004a  stloc.s  0xA
0x1004c  ldloc.s  0xA
0x1004e  ldstr    aPostponeuntil// "postponeuntil"
0x10053  ldloc.s  7
0x10055  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime)
0x1005a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x1005f  ldloc.s  0xA
0x10061  ldstr    aAsyncoperation// "asyncoperationid"
0x10066  ldloc.1
0x10067  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x1006c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x10071  ldloc.2
0x10072  ldloc.s  0xA
0x10074  ldarg.0
0x10075  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1007a  ldarg.0
0x1007b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x10080  ldc.i4.s 0x15
0x10082  ldstr    a0// "{0}"
0x10087  ldc.i4.1
0x10088  newarr   [mscorlib]System.Object
0x1008d  dup
0x1008e  ldc.i4.0
0x1008f  ldstr    aKnowledgeArtic_1// "Knowledge Article Asyncjob rescheduled "...
0x10094  ldloc.s  6
0x10096  box      [mscorlib]System.DateTime
0x1009b  ldloc.s  0xA
0x1009d  ldstr    aPostponeuntil// "postponeuntil"
0x100a2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x100a7  call     string [mscorlib]System.String::Format(string, object, object)
0x100ac  stelem.ref
0x100ad  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x100b2  leave.s  loc_100F6
0x100b4  ldnull
0x100b5  ldarg.0
0x100b6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x100bb  ldc.i4.s 0x15
0x100bd  ldstr    aRecurringAsync_1// "Recurring Async job {0} for Knowledge M"...
0x100c2  ldc.i4.1
0x100c3  newarr   [mscorlib]System.Object
0x100c8  dup
0x100c9  ldc.i4.0
0x100ca  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Service.ObjectModel.KnowledgeArticleHelper::GetKnowledgeArticleAsyncJobId()
0x100cf  box      [mscorlib]System.Guid
0x100d4  stelem.ref
0x100d5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x100da  ldstr    aAsyncJobForKno// "Async Job for Knowledge Management was "...
0x100df  ldc.i4   0x80044164
0x100e4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x100e9  throw
0x100ea  leave.s  loc_100F6
0x100ec  ldloc.0
0x100ed  brfalse.s loc_100F5
0x100ef  ldloc.0
0x100f0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x100f5  endfinally
0x100f6  ret
```
