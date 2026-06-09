# Microsoft.Crm.CrmLive.Services.ServiceInstanceService::GetServiceInstance

- ea: `0x129a0`
- end: `0x12a1f`
- name: `Microsoft.Crm.CrmLive.Services.ServiceInstanceService::GetServiceInstance`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x12910`

## callees

- `0x129a0`
- `0x12fb0`
- `0x13060`

## string_xrefs

- `0x129f5`: `ServiceComponentId`
- `0x12a01`: `ServiceInstanceId`
- `0x129ac`: `serviceInstanceId`

## pseudocode

```c

```

## disassembly

```asm
0x129a0  ldarg.0
0x129a1  ldstr    aPuid// "puid"
0x129a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x129ab  ldarg.1
0x129ac  ldstr    aServiceinstanc_1// "serviceInstanceId"
0x129b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x129b6  ldnull
0x129b7  stloc.0
0x129b8  ldarg.0
0x129b9  ldarg.1
0x129ba  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.CrmLive.Services.ServiceInstanceService::TryGetServiceInstance(string puid, string serviceInstanceId)
0x129bf  stloc.0
0x129c0  ldloc.0
0x129c1  brtrue.s loc_129CA
0x129c3  ldarg.1
0x129c4  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.CrmLive.Services.ServiceInstanceService::TryGetServiceInstanceMatchesSku(string serviceInstanceId)
0x129c9  stloc.0
0x129ca  ldloc.0
0x129cb  brtrue.s loc_12A1D
0x129cd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x129d2  stloc.0
0x129d3  ldloc.0
0x129d4  ldstr    aFriendlyname// "FriendlyName"
0x129d9  ldnull
0x129da  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x129df  ldloc.0
0x129e0  ldstr    aOrganizationid_0// "OrganizationId"
0x129e5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x129ea  box      [mscorlib]System.Guid
0x129ef  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x129f4  ldloc.0
0x129f5  ldstr    aServicecompone// "ServiceComponentId"
0x129fa  ldnull
0x129fb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12a00  ldloc.0
0x12a01  ldstr    aServiceinstanc_0// "ServiceInstanceId"
0x12a06  ldnull
0x12a07  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12a0c  ldloc.0
0x12a0d  ldstr    aStatuscode// "StatusCode"
0x12a12  ldc.i4.0
0x12a13  box      [mscorlib]System.Int32
0x12a18  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12a1d  ldloc.0
0x12a1e  ret
```
