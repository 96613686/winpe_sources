# Microsoft.Crm.CrmLive.Services.ServiceInstanceService::SetServiceInstancesStatusForOrganization

- ea: `0x134e0`
- end: `0x135ce`
- name: `Microsoft.Crm.CrmLive.Services.ServiceInstanceService::SetServiceInstancesStatusForOrganization`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x12780`
- `0x127a0`
- `0x127c0`
- `0x127e0`
- `0x12800`
- `0x12820`
- `0x12840`
- `0x12860`
- `0x12dd0`
- `0x12df0`
- `0x13480`
- `0x134e0`

## string_xrefs

- `0x13554`: `ServiceComponentId`
- `0x1358c`: `ServiceComponentId`
- `0x1356a`: `ServiceInstanceId`

## pseudocode

```c

```

## disassembly

```asm
0x134e0  ldarg.1
0x134e1  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.CrmLive.Services.ServiceInstanceService::RetrieveServiceInstancesForOrganization(valuetype [mscorlib]System.Guid orgId)
0x134e6  stloc.0
0x134e7  ldloc.0
0x134e8  brfalse  loc_135CD
0x134ed  ldloc.0
0x134ee  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x134f3  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x134f8  stloc.1
0x134f9  br       loc_135B1
0x134fe  ldloca.s 1
0x13500  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x13505  stloc.2
0x13506  newobj   instance void Microsoft.Crm.CrmLive.Services.ServiceInstance::.ctor()
0x1350b  dup
0x1350c  ldloc.2
0x1350d  ldstr    aFriendlyname// "FriendlyName"
0x13512  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x13517  castclass [mscorlib]System.String
0x1351c  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceInstance::set_ServiceInstanceFriendlyName(string value)
0x13521  dup
0x13522  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x13527  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceInstance::set_Id(valuetype [mscorlib]System.Guid value)
0x1352c  dup
0x1352d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x13532  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceInstance::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x13537  dup
0x13538  ldloc.2
0x13539  ldstr    aPuid_0// "Puid"
0x1353e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x13543  castclass [mscorlib]System.String
0x13548  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.Puid [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.Puid::CreateTextPuid(string)
0x1354d  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceInstance::set_UserPuid(class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.Puid value)
0x13552  dup
0x13553  ldloc.2
0x13554  ldstr    aServicecompone// "ServiceComponentId"
0x13559  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1355e  castclass [mscorlib]System.String
0x13563  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceInstance::set_ServiceComponentId(string value)
0x13568  dup
0x13569  ldloc.2
0x1356a  ldstr    aServiceinstanc_0// "ServiceInstanceId"
0x1356f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x13574  castclass [mscorlib]System.String
0x13579  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceInstance::set_ServiceInstanceId(string value)
0x1357e  dup
0x1357f  ldarg.2
0x13580  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceInstance::set_ServiceInstanceStatus(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ServiceInstanceStatus value)
0x13585  call     void Microsoft.Crm.CrmLive.Services.ServiceInstanceService::SetServiceInstance(class Microsoft.Crm.CrmLive.Services.ServiceInstance input)
0x1358a  ldarg.1
0x1358b  ldloc.2
0x1358c  ldstr    aServicecompone// "ServiceComponentId"
0x13591  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x13596  castclass [mscorlib]System.String
0x1359b  ldarg.2
0x1359c  ldloc.2
0x1359d  ldstr    aStatuscode// "StatusCode"
0x135a2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x135a7  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ServiceInstanceStatus
0x135ac  call     void Microsoft.Crm.CrmLive.Services.ServiceInstanceService::SetOrganizationResources(valuetype [mscorlib]System.Guid orgId, string serviceComponentId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ServiceInstanceStatus statusCode, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ServiceInstanceStatus oldStatusCode)
0x135b1  ldloca.s 1
0x135b3  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x135b8  brtrue   loc_134FE
0x135bd  leave.s  loc_135CD
0x135bf  ldloca.s 1
0x135c1  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x135c7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x135cc  endfinally
0x135cd  ret
```
