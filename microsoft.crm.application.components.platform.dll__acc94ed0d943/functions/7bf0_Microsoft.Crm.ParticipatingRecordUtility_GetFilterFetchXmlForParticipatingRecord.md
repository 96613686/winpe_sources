# Microsoft.Crm.ParticipatingRecordUtility::GetFilterFetchXmlForParticipatingRecord

- ea: `0x7bf0`
- end: `0x7d20`
- name: `Microsoft.Crm.ParticipatingRecordUtility::GetFilterFetchXmlForParticipatingRecord`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x9f900`
- `0x9fa40`

## callees

- `0x7bf0`
- `0x7d20`
- `0x7e50`
- `0x30e30`
- `0x30e70`
- `0x59e40`
- `0x5be20`

## string_xrefs

- `0x7c0f`: `consideronlygoalownersrecords`
- `0x7ca4`: `consideronlygoalownersrecords`
- `0x7c5b`: `fetchxml`
- `0x7c7d`: `fetchxml`
- `0x7c8b`: `fetchxml`

## pseudocode

```c

```

## disassembly

```asm
0x7bf0  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor()
0x7bf5  stloc.0
0x7bf6  ldloc.0
0x7bf7  ldc.i4.7
0x7bf8  newarr   [mscorlib]System.String
0x7bfd  dup
0x7bfe  ldc.i4.0
0x7bff  ldstr    aGoalid// "goalid"
0x7c04  stelem.ref
0x7c05  dup
0x7c06  ldc.i4.1
0x7c07  ldstr    aGoalownerid// "goalownerid"
0x7c0c  stelem.ref
0x7c0d  dup
0x7c0e  ldc.i4.2
0x7c0f  ldstr    aConsideronlygo// "consideronlygoalownersrecords"
0x7c14  stelem.ref
0x7c15  dup
0x7c16  ldc.i4.3
0x7c17  ldstr    aRolluponlyfrom// "rolluponlyfromchildgoals"
0x7c1c  stelem.ref
0x7c1d  dup
0x7c1e  ldc.i4.4
0x7c1f  ldstr    aGoalstartdate// "goalstartdate"
0x7c24  stelem.ref
0x7c25  dup
0x7c26  ldc.i4.5
0x7c27  ldstr    aGoalenddate// "goalenddate"
0x7c2c  stelem.ref
0x7c2d  dup
0x7c2e  ldc.i4.6
0x7c2f  ldstr    aOwnerid// "ownerid"
0x7c34  stelem.ref
0x7c35  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x7c3a  ldstr    aGoal// "goal"
0x7c3f  ldarg.0
0x7c40  ldloc.0
0x7c41  ldc.i4.1
0x7c42  ldarg.3
0x7c43  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase columnSet, bool useSystemUserContext, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x7c48  ldnull
0x7c49  stloc.1
0x7c4a  ldarg.2
0x7c4b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7c50  brtrue.s loc_7C9B
0x7c52  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor()
0x7c57  stloc.s  9
0x7c59  ldloc.s  9
0x7c5b  ldstr    aFetchxml// "fetchxml"
0x7c60  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x7c65  ldstr    aGoalrollupquer// "goalrollupquery"
0x7c6a  ldarg.2
0x7c6b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7c70  ldloc.s  9
0x7c72  ldc.i4.1
0x7c73  ldarg.3
0x7c74  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase columnSet, bool useSystemUserContext, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x7c79  stloc.s  0xA
0x7c7b  ldloc.s  0xA
0x7c7d  ldstr    aFetchxml// "fetchxml"
0x7c82  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x7c87  brfalse.s loc_7C9B
0x7c89  ldloc.s  0xA
0x7c8b  ldstr    aFetchxml// "fetchxml"
0x7c90  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x7c95  castclass [mscorlib]System.String
0x7c9a  stloc.1
0x7c9b  ldarg.1
0x7c9c  ldarg.3
0x7c9d  call     class Microsoft.Crm.MetricInfo Microsoft.Crm.ParticipatingRecordUtility::GetMetricInfo(valuetype [mscorlib]System.Guid metricDetailId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x7ca2  stloc.2
0x7ca3  dup
0x7ca4  ldstr    aConsideronlygo// "consideronlygoalownersrecords"
0x7ca9  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x7cae  unbox.any [mscorlib]System.Boolean
0x7cb3  stloc.3
0x7cb4  dup
0x7cb5  ldstr    aGoalownerid// "goalownerid"
0x7cba  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x7cbf  castclass Microsoft.Crm.Application.Types.LookupValue
0x7cc4  dup
0x7cc5  callvirt instance string Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x7cca  stloc.s  4
0x7ccc  callvirt instance int32 Microsoft.Crm.Application.Types.LookupValue::get_Type()
0x7cd1  stloc.s  5
0x7cd3  dup
0x7cd4  ldstr    aOwnerid// "ownerid"
0x7cd9  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x7cde  castclass Microsoft.Crm.Application.Types.LookupValue
0x7ce3  callvirt instance string Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x7ce8  stloc.s  6
0x7cea  dup
0x7ceb  ldstr    aGoalstartdate// "goalstartdate"
0x7cf0  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x7cf5  unbox.any [mscorlib]System.DateTime
0x7cfa  stloc.s  7
0x7cfc  ldstr    aGoalenddate// "goalenddate"
0x7d01  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x7d06  unbox.any [mscorlib]System.DateTime
0x7d0b  stloc.s  8
0x7d0d  ldloc.1
0x7d0e  ldloc.2
0x7d0f  ldloc.3
0x7d10  ldloc.s  4
0x7d12  ldloc.s  5
0x7d14  ldloc.s  7
0x7d16  ldloc.s  8
0x7d18  ldloc.s  6
0x7d1a  call     string Microsoft.Crm.ParticipatingRecordUtility::CreateFetchXmlsForParticipatingRecords(string participatingRecordsFetchXml, class Microsoft.Crm.MetricInfo rollupMetric, bool addGoalOwnerFilter, string goalOwnerId, int32 goalOwnerIdType, valuetype [mscorlib]System.DateTime goalStartDate, valuetype [mscorlib]System.DateTime goalEndDate, string goalManagerId)
0x7d1f  ret
```
