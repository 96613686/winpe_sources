# Microsoft.Crm.ObjectModel.GenericActivityServiceBase::ThrowIfInvalidForUpdate

- ea: `0x5cf20`
- end: `0x5d0b3`
- name: `Microsoft.Crm.ObjectModel.GenericActivityServiceBase::ThrowIfInvalidForUpdate`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x5cd30`

## callees

- `0x5cf20`
- `0x5d0c0`
- `0x5d1c0`
- `0x5e740`

## string_xrefs

- `0x5cf9f`: `scheduledstart`
- `0x5d000`: `scheduledstart`
- `0x5d02d`: `scheduledstart`
- `0x5d086`: `scheduledstart`
- `0x5cfaf`: `scheduledend`
- `0x5d00d`: `scheduledend`
- `0x5d04b`: `scheduledend`
- `0x5d096`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x5cf20  ldarg.0
0x5cf21  ldfld    class Microsoft.Crm.ObjectModel.RecurringSeriesContext Microsoft.Crm.ObjectModel.GenericActivityServiceBase::seriesContext
0x5cf26  callvirt instance bool Microsoft.Crm.ObjectModel.RecurringSeriesContext::get_IsSeriesOperation()
0x5cf2b  brfalse.s loc_5CF2E
0x5cf2d  ret
0x5cf2e  ldloca.s 0
0x5cf30  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ActivityState>
0x5cf36  ldarg.1
0x5cf37  ldstr    aStatecode// "statecode"
0x5cf3c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x5cf41  brtrue.s loc_5CF5A
0x5cf43  ldloca.s 0
0x5cf45  ldarg.1
0x5cf46  ldstr    aStatecode// "statecode"
0x5cf4b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5cf50  unbox.any [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ActivityState
0x5cf55  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ActivityState>::.ctor(var<u1>)
0x5cf5a  ldarg.1
0x5cf5b  ldstr    aActivityid_0// "activityid"
0x5cf60  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5cf65  unbox.any [mscorlib]System.Guid
0x5cf6a  ldarg.1
0x5cf6b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x5cf70  ldarg.2
0x5cf71  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5cf76  stloc.1
0x5cf77  ldarg.1
0x5cf78  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x5cf7d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5cf82  ldarg.2
0x5cf83  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x5cf88  stloc.2
0x5cf89  ldloc.2
0x5cf8a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5cf8f  ldstr    aStatecode// "statecode"
0x5cf94  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x5cf99  ldloc.2
0x5cf9a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5cf9f  ldstr    aScheduledstart// "scheduledstart"
0x5cfa4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x5cfa9  ldloc.2
0x5cfaa  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5cfaf  ldstr    aScheduledend// "scheduledend"
0x5cfb4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x5cfb9  ldarg.2
0x5cfba  ldc.i4.1
0x5cfbb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x5cfc0  stloc.s  9
0x5cfc2  ldarg.0
0x5cfc3  ldloc.1
0x5cfc4  ldloc.2
0x5cfc5  ldarg.2
0x5cfc6  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5cfcb  stloc.3
0x5cfcc  leave.s  loc_5CFDA
0x5cfce  ldloc.s  9
0x5cfd0  brfalse.s loc_5CFD9
0x5cfd2  ldloc.s  9
0x5cfd4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5cfd9  endfinally
0x5cfda  ldloc.3
0x5cfdb  ldstr    aStatecode// "statecode"
0x5cfe0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5cfe5  unbox.any [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ActivityState
0x5cfea  stloc.s  4
0x5cfec  ldarg.0
0x5cfed  ldarg.1
0x5cfee  callvirt instance bool [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::HasUpdatableAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x5cff3  brtrue.s loc_5CFFF
0x5cff5  ldarg.0
0x5cff6  ldloc.s  4
0x5cff8  ldarg.2
0x5cff9  ldloc.0
0x5cffa  callvirt instance void Microsoft.Crm.ObjectModel.GenericActivityServiceBase::ThrowIfClosedOrCanceled(valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ActivityState stateCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ActivityState> targetStateCode)
0x5cfff  ldarg.1
0x5d000  ldstr    aScheduledstart// "scheduledstart"
0x5d005  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5d00a  stloc.s  5
0x5d00c  ldarg.1
0x5d00d  ldstr    aScheduledend// "scheduledend"
0x5d012  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5d017  stloc.s  6
0x5d019  ldnull
0x5d01a  stloc.s  7
0x5d01c  ldnull
0x5d01d  stloc.s  8
0x5d01f  ldloc.s  5
0x5d021  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d026  beq.s    loc_5D03D
0x5d028  ldloc.s  5
0x5d02a  brtrue.s loc_5D039
0x5d02c  ldloc.3
0x5d02d  ldstr    aScheduledstart// "scheduledstart"
0x5d032  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5d037  br.s     loc_5D03B
0x5d039  ldloc.s  5
0x5d03b  stloc.s  7
0x5d03d  ldloc.s  6
0x5d03f  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d044  beq.s    loc_5D05B
0x5d046  ldloc.s  6
0x5d048  brtrue.s loc_5D057
0x5d04a  ldloc.3
0x5d04b  ldstr    aScheduledend// "scheduledend"
0x5d050  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5d055  br.s     loc_5D059
0x5d057  ldloc.s  6
0x5d059  stloc.s  8
0x5d05b  ldloc.s  5
0x5d05d  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d062  bne.un.s loc_5D06D
0x5d064  ldloc.s  6
0x5d066  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d06b  bne.un.s loc_5D07F
0x5d06d  ldloc.s  5
0x5d06f  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d074  beq.s    loc_5D0A5
0x5d076  ldloc.s  6
0x5d078  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d07d  bne.un.s loc_5D0A5
0x5d07f  ldnull
0x5d080  stloc.s  7
0x5d082  ldnull
0x5d083  stloc.s  8
0x5d085  ldarg.1
0x5d086  ldstr    aScheduledstart// "scheduledstart"
0x5d08b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d090  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d095  ldarg.1
0x5d096  ldstr    aScheduledend// "scheduledend"
0x5d09b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d0a0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d0a5  ldarg.0
0x5d0a6  ldarg.1
0x5d0a7  ldloc.s  7
0x5d0a9  ldloc.s  8
0x5d0ab  ldarg.2
0x5d0ac  ldc.i4.0
0x5d0ad  call     instance void Microsoft.Crm.ObjectModel.GenericActivityServiceBase::SetScheduledDurationMinute(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, object scheduledStart, object scheduledEnd, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool isCreate)
0x5d0b2  ret
```
