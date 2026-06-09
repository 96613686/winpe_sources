# Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::Reschedule

- ea: `0x340`
- end: `0x4e2`
- name: `Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::Reschedule`
- size: `418`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x340`

## string_xrefs

- `0x39b`: `scheduledstart`
- `0x3a3`: `scheduledend`
- `0x34f`: `Reschedule expected serviceappointment entity, received {0}`
- `0x3c3`: `serviceid`

## pseudocode

```c

```

## disassembly

```asm
0x340  ldarg.1
0x341  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceAppointment
0x346  stloc.0
0x347  ldloc.0
0x348  brtrue.s loc_373
0x34a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x34f  ldstr    aRescheduleExpe// "Reschedule expected serviceappointment "...
0x354  ldc.i4.1
0x355  newarr   [mscorlib]System.Object
0x35a  dup
0x35b  ldc.i4.0
0x35c  ldarg.1
0x35d  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x362  stelem.ref
0x363  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x368  ldstr    aAppointment// "appointment"
0x36d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x372  throw
0x373  ldarg.0
0x374  ldloc.0
0x375  ldarg.2
0x376  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CommunicationActivityServiceBase::ResolveUnresolvedParties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x37b  ldloc.0
0x37c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x381  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x386  ldarg.2
0x387  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x38c  stloc.1
0x38d  ldloc.1
0x38e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x393  ldc.i4.7
0x394  newarr   [mscorlib]System.String
0x399  dup
0x39a  ldc.i4.0
0x39b  ldstr    aScheduledstart// "scheduledstart"
0x3a0  stelem.ref
0x3a1  dup
0x3a2  ldc.i4.1
0x3a3  ldstr    aScheduledend// "scheduledend"
0x3a8  stelem.ref
0x3a9  dup
0x3aa  ldc.i4.2
0x3ab  ldstr    aResources// "resources"
0x3b0  stelem.ref
0x3b1  dup
0x3b2  ldc.i4.3
0x3b3  ldstr    aCustomers// "customers"
0x3b8  stelem.ref
0x3b9  dup
0x3ba  ldc.i4.4
0x3bb  ldstr    aSiteid// "siteid"
0x3c0  stelem.ref
0x3c1  dup
0x3c2  ldc.i4.5
0x3c3  ldstr    aServiceid// "serviceid"
0x3c8  stelem.ref
0x3c9  dup
0x3ca  ldc.i4.6
0x3cb  ldstr    aIsalldayevent// "isalldayevent"
0x3d0  stelem.ref
0x3d1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x3d6  ldloc.0
0x3d7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x3dc  unbox.any [mscorlib]System.Guid
0x3e1  ldloc.0
0x3e2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x3e7  ldarg.2
0x3e8  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3ed  stloc.2
0x3ee  ldarg.2
0x3ef  ldc.i4.1
0x3f0  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x3f5  stloc.s  5
0x3f7  ldarg.0
0x3f8  ldloc.2
0x3f9  ldloc.1
0x3fa  ldarg.2
0x3fb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x400  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceAppointment
0x405  stloc.3
0x406  leave.s  loc_414
0x408  ldloc.s  5
0x40a  brfalse.s loc_413
0x40c  ldloc.s  5
0x40e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x413  endfinally
0x414  ldloc.3
0x415  ldloc.0
0x416  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Merge(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x41b  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceAppointment
0x420  stloc.s  4
0x422  ldloc.3
0x423  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceAppointment::get_Resources()
0x428  brfalse  loc_4D3
0x42d  ldloc.3
0x42e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceAppointment::get_Resources()
0x433  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_EntityName()
0x438  brfalse  loc_4D3
0x43d  ldloc.3
0x43e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceAppointment::get_Resources()
0x443  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_EntityName()
0x448  ldstr    aActivityparty// "ActivityParty"
0x44d  ldc.i4.5
0x44e  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x453  brfalse.s loc_4D3
0x455  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x45a  stloc.s  6
0x45c  ldloc.3
0x45d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ServiceAppointment::get_Resources()
0x462  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x467  stloc.s  7
0x469  br.s     loc_49B
0x46b  ldloc.s  7
0x46d  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x472  castclass [Microsoft.Crm.Common.Entities]Microsoft.Crm.Common.Entities.ActivityParty
0x477  stloc.s  8
0x479  ldloc.s  6
0x47b  ldloc.s  8
0x47d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x482  ldstr    aPartyid// "partyid"
0x487  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x48c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x491  unbox.any [mscorlib]System.Guid
0x496  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x49b  ldloc.s  7
0x49d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a2  brtrue.s loc_46B
0x4a4  leave.s  loc_4BB
0x4a6  ldloc.s  7
0x4a8  isinst   [mscorlib]System.IDisposable
0x4ad  stloc.s  9
0x4af  ldloc.s  9
0x4b1  brfalse.s loc_4BA
0x4b3  ldloc.s  9
0x4b5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ba  endfinally
0x4bb  ldloc.s  6
0x4bd  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x4c2  newobj   instance void [Microsoft.Crm.Scheduling]Microsoft.Crm.Scheduling.InvalidateScheduleCacheCommand::.ctor(valuetype [mscorlib]System.Guid[])
0x4c7  ldarg.2
0x4c8  newobj   instance void [Microsoft.Crm.Scheduling]Microsoft.Crm.Scheduling.CrmSchedulingExecutionContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4cd  callvirt instance object [Microsoft.Crm.Scheduling]Microsoft.Crm.Scheduling.InvalidateScheduleCacheCommand::Execute(class [Microsoft.Crm.Scheduling]Microsoft.Crm.Scheduling.ISchedulingExecutionContext)
0x4d2  pop
0x4d3  ldarg.0
0x4d4  ldfld    class [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ScheduleService Microsoft.Crm.Service.ObjectModel.ServiceAppointmentService::_scheduleService
0x4d9  ldloc.s  4
0x4db  ldarg.2
0x4dc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.ValidationResult [Microsoft.Crm.Common.ObjectModel]Microsoft.Crm.Common.ObjectModel.ScheduleService::Reschedule(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CommunicationActivity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4e1  ret
```
