# Microsoft.Crm.ObjectModel.SubscriptionService::RetrieveState

- ea: `0x159fb0`
- end: `0x15a088`
- name: `Microsoft.Crm.ObjectModel.SubscriptionService::RetrieveState`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x164b10`

## callees

- `0x159fb0`

## string_xrefs

- `0x159fc4`: `completedsyncstartedon`
- `0x15a057`: `completedsyncstartedon`
- `0x15a069`: `completedsyncstartedon`
- `0x15a078`: `completedsyncstartedon`
- `0x159fd4`: `completedsyncversionnumber`
- `0x15a020`: `completedsyncversionnumber`
- `0x15a032`: `completedsyncversionnumber`
- `0x15a046`: `completedsyncversionnumber`

## pseudocode

```c

```

## disassembly

```asm
0x159fb0  ldarg.0
0x159fb1  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x159fb6  ldarg.s  4
0x159fb8  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x159fbd  stloc.0
0x159fbe  ldloc.0
0x159fbf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x159fc4  ldstr    aCompletedsyncs// "completedsyncstartedon"
0x159fc9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x159fce  ldloc.0
0x159fcf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x159fd4  ldstr    aCompletedsyncv_0// "completedsyncversionnumber"
0x159fd9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x159fde  ldloc.0
0x159fdf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x159fe4  ldstr    aReinitialize// "reinitialize"
0x159fe9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x159fee  ldarg.1
0x159fef  ldarg.0
0x159ff0  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x159ff5  ldarg.s  4
0x159ff7  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x159ffc  stloc.1
0x159ffd  ldarg.0
0x159ffe  ldloc.1
0x159fff  ldloc.0
0x15a000  ldarg.s  4
0x15a002  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x15a007  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Subscription
0x15a00c  stloc.2
0x15a00d  ldarg.3
0x15a00e  ldloc.2
0x15a00f  ldstr    aReinitialize// "reinitialize"
0x15a014  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x15a019  unbox.any [mscorlib]System.Boolean
0x15a01e  stind.i1
0x15a01f  ldloc.2
0x15a020  ldstr    aCompletedsyncv_0// "completedsyncversionnumber"
0x15a025  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x15a02a  brfalse.s loc_15A03E
0x15a02c  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15a031  ldloc.2
0x15a032  ldstr    aCompletedsyncv_0// "completedsyncversionnumber"
0x15a037  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x15a03c  bne.un.s loc_15A044
0x15a03e  ldarg.2
0x15a03f  ldc.i4.0
0x15a040  conv.i8
0x15a041  stind.i8
0x15a042  br.s     loc_15A056
0x15a044  ldarg.2
0x15a045  ldloc.2
0x15a046  ldstr    aCompletedsyncv_0// "completedsyncversionnumber"
0x15a04b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x15a050  unbox.any [mscorlib]System.Int64
0x15a055  stind.i8
0x15a056  ldloc.2
0x15a057  ldstr    aCompletedsyncs// "completedsyncstartedon"
0x15a05c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x15a061  brfalse.s loc_15A075
0x15a063  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x15a068  ldloc.2
0x15a069  ldstr    aCompletedsyncs// "completedsyncstartedon"
0x15a06e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x15a073  bne.un.s loc_15A077
0x15a075  ldnull
0x15a076  ret
0x15a077  ldloc.2
0x15a078  ldstr    aCompletedsyncs// "completedsyncstartedon"
0x15a07d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x15a082  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x15a087  ret
```
