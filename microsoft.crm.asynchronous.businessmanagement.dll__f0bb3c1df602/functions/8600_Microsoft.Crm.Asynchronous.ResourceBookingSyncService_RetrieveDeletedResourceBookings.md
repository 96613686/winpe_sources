# Microsoft.Crm.Asynchronous.ResourceBookingSyncService::RetrieveDeletedResourceBookings

- ea: `0x8600`
- end: `0x8724`
- name: `Microsoft.Crm.Asynchronous.ResourceBookingSyncService::RetrieveDeletedResourceBookings`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x67f0`

## callees

- `0x8600`
- `0x8730`
- `0x8ab0`
- `0x13d30`
- `0x142c0`
- `0x14db0`
- `0x15e20`
- `0x16390`
- `0x163e0`

## string_xrefs

- `0x86cb`: `isdeletedinexchange`
- `0x8606`: `MethodRetrieveDeletedResourceBookings`
- `0x8719`: `MethodRetrieveDeletedResourceBookings`
- `0x861c`: `MethodRetrieveDeletedResourceBookings_RetrieveFromTracking`
- `0x8648`: `MethodRetrieveDeletedResourceBookings_RetrieveFromTracking`

## pseudocode

```c

```

## disassembly

```asm
0x8600  ldarg.0
0x8601  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8606  ldstr    aMethodretrieve// "MethodRetrieveDeletedResourceBookings"
0x860b  callvirt instance void Metrics::StartTimer(string name)
0x8610  ldarg.1
0x8611  brfalse  loc_8713
0x8616  ldarg.0
0x8617  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x861c  ldstr    aMethodretrieve_0// "MethodRetrieveDeletedResourceBookings_R"...
0x8621  callvirt instance void Metrics::StartTimer(string name)
0x8626  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ResourceBookingSyncService::get_OrganizationId()
0x862b  ldarg.0
0x862c  ldfld    class ConfigurationSettings Microsoft.Crm.Asynchronous.ResourceBookingSyncService::Settings
0x8631  callvirt instance int32 ConfigurationSettings::get_ObjectTypeCode()
0x8636  ldarg.2
0x8637  newobj   instance void SubscriptionTrackingDeletedObjectQuerySQL::.ctor(valuetype [mscorlib]System.Guid organizationId, int32 objectTypeCode, int64 minVersionNumber)
0x863c  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> NonPagedQuery::Next()
0x8641  stloc.0
0x8642  ldarg.0
0x8643  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8648  ldstr    aMethodretrieve_0// "MethodRetrieveDeletedResourceBookings_R"...
0x864d  callvirt instance void Metrics::StopTimer(string name)
0x8652  ldloc.0
0x8653  brfalse  loc_8713
0x8658  ldloc.0
0x8659  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x865e  stloc.1
0x865f  br       loc_86FC
0x8664  ldloc.1
0x8665  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x866a  ldstr    aBookableresour_1// "bookableresourcebookingid"
0x866f  callvirt T0x2B000010
0x8674  stloc.2
0x8675  ldloc.2
0x8676  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x867b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8680  brfalse.s loc_86FC
0x8682  ldarg.0
0x8683  ldloc.2
0x8684  ldc.i4.0
0x8685  call     instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ResourceBookingSyncService::GetIdMappingsForBookableResourceBooking(valuetype [mscorlib]System.Guid bookableResourceBookingId, bool includeDeletedInExchange)
0x868a  stloc.3
0x868b  ldloc.3
0x868c  brfalse.s loc_86FC
0x868e  ldloc.3
0x868f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x8694  stloc.s  4
0x8696  br.s     loc_86E5
0x8698  ldloc.s  4
0x869a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x869f  dup
0x86a0  ldstr    aUserid// "userid"
0x86a5  callvirt T0x2B000013
0x86aa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x86af  stloc.s  5
0x86b1  dup
0x86b2  ldstr    aExchangeentryi// "exchangeentryid"
0x86b7  callvirt T0x2B000011
0x86bc  stloc.s  6
0x86be  dup
0x86bf  ldstr    aBookableresour// "bookableresourcebookingexchangesyncidma"...
0x86c4  callvirt T0x2B000010
0x86c9  stloc.s  7
0x86cb  ldstr    aIsdeletedinexc// "isdeletedinexchange"
0x86d0  callvirt T0x2B000014
0x86d5  brtrue.s loc_86E5
0x86d7  ldarg.1
0x86d8  ldloc.s  5
0x86da  ldloc.s  6
0x86dc  ldc.i4.0
0x86dd  ldloc.s  7
0x86df  callvirt instance bool SyncDeleteCollection::Add(valuetype [mscorlib]System.Guid userId, string exchangeId, bool keepIdMappingAfterExchangeDelete, valuetype [mscorlib]System.Guid mappingId)
0x86e4  pop
0x86e5  ldloc.s  4
0x86e7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x86ec  brtrue.s loc_8698
0x86ee  leave.s  loc_86FC
0x86f0  ldloc.s  4
0x86f2  brfalse.s loc_86FB
0x86f4  ldloc.s  4
0x86f6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x86fb  endfinally
0x86fc  ldloc.1
0x86fd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8702  brtrue   loc_8664
0x8707  leave.s  loc_8713
0x8709  ldloc.1
0x870a  brfalse.s loc_8712
0x870c  ldloc.1
0x870d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8712  endfinally
0x8713  ldarg.0
0x8714  ldfld    class Metrics Microsoft.Crm.Asynchronous.ResourceBookingSyncService::metrics
0x8719  ldstr    aMethodretrieve// "MethodRetrieveDeletedResourceBookings"
0x871e  callvirt instance void Metrics::StopTimer(string name)
0x8723  ret
```
