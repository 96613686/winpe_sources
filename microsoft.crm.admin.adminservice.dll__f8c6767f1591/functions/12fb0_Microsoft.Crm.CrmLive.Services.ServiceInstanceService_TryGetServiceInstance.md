# Microsoft.Crm.CrmLive.Services.ServiceInstanceService::TryGetServiceInstance

- ea: `0x12fb0`
- end: `0x13055`
- name: `Microsoft.Crm.CrmLive.Services.ServiceInstanceService::TryGetServiceInstance`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x129a0`
- `0x12df0`

## callees

- `0x12fb0`

## string_xrefs

- `0x12ffa`: `ServiceComponentId`
- `0x12fd5`: `ServiceInstance`
- `0x13024`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`
- `0x12fc9`: `ServiceInstanceId`
- `0x1300a`: `ServiceInstanceId`
- `0x1301f`: `TryGetServiceInstance`

## pseudocode

```c

```

## disassembly

```asm
0x12fb0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x12fb5  stloc.0
0x12fb6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x12fbb  stloc.1
0x12fbc  ldloc.1
0x12fbd  ldstr    aPuid_0// "Puid"
0x12fc2  ldarg.0
0x12fc3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12fc8  ldloc.1
0x12fc9  ldstr    aServiceinstanc_0// "ServiceInstanceId"
0x12fce  ldarg.1
0x12fcf  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12fd4  ldloc.0
0x12fd5  ldstr    aServiceinstanc// "ServiceInstance"
0x12fda  ldc.i4.6
0x12fdb  newarr   [mscorlib]System.String
0x12fe0  dup
0x12fe1  ldc.i4.0
0x12fe2  ldstr    aFriendlyname// "FriendlyName"
0x12fe7  stelem.ref
0x12fe8  dup
0x12fe9  ldc.i4.1
0x12fea  ldstr    aId// "Id"
0x12fef  stelem.ref
0x12ff0  dup
0x12ff1  ldc.i4.2
0x12ff2  ldstr    aOrganizationid_0// "OrganizationId"
0x12ff7  stelem.ref
0x12ff8  dup
0x12ff9  ldc.i4.3
0x12ffa  ldstr    aServicecompone// "ServiceComponentId"
0x12fff  stelem.ref
0x13000  dup
0x13001  ldc.i4.4
0x13002  ldstr    aStatuscode// "StatusCode"
0x13007  stelem.ref
0x13008  dup
0x13009  ldc.i4.5
0x1300a  ldstr    aServiceinstanc_0// "ServiceInstanceId"
0x1300f  stelem.ref
0x13010  ldc.i4.1
0x13011  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x13016  dup
0x13017  ldc.i4.0
0x13018  ldloc.1
0x13019  stelem.ref
0x1301a  ldc.i4   0x14B
0x1301f  ldstr    aTrygetservicei// "TryGetServiceInstance"
0x13024  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x13029  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x1302e  stloc.2
0x1302f  ldloc.2
0x13030  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x13035  brtrue.s loc_13045
0x13037  ldloc.2
0x13038  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x1303d  call     T0x2B00005D
0x13042  stloc.3
0x13043  leave.s  loc_13053
0x13045  leave.s  loc_13051
0x13047  ldloc.0
0x13048  brfalse.s loc_13050
0x1304a  ldloc.0
0x1304b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13050  endfinally
0x13051  ldnull
0x13052  ret
0x13053  ldloc.3
0x13054  ret
```
