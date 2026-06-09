# Microsoft.Crm.CrmLive.Services.ServiceInstanceService::SetServiceInstance

- ea: `0x12df0`
- end: `0x12f98`
- name: `Microsoft.Crm.CrmLive.Services.ServiceInstanceService::SetServiceInstance`
- size: `424`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x13350`
- `0x134e0`

## callees

- `0x12790`
- `0x127b0`
- `0x127d0`
- `0x127f0`
- `0x12810`
- `0x12830`
- `0x12850`
- `0x12df0`
- `0x12fb0`
- `0x13060`

## string_xrefs

- `0x12edb`: `ServiceComponentId`
- `0x12f53`: `ServiceComponentId`
- `0x12e11`: `ServiceInstance`
- `0x12f15`: `ServiceInstance`
- `0x12f64`: `ServiceInstance`
- `0x12e2c`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`
- `0x12f26`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`
- `0x12f80`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`
- `0x12eed`: `ServiceInstanceId`
- `0x12e27`: `SetServiceInstance`
- `0x12f21`: `SetServiceInstance`
- `0x12f7b`: `SetServiceInstance`

## pseudocode

```c

```

## disassembly

```asm
0x12df0  ldarg.0
0x12df1  ldstr    aInput// "input"
0x12df6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x12dfb  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x12e00  stloc.0
0x12e01  ldc.i4.1
0x12e02  newarr   [mscorlib]System.String
0x12e07  dup
0x12e08  ldc.i4.0
0x12e09  ldstr    aId// "Id"
0x12e0e  stelem.ref
0x12e0f  stloc.1
0x12e10  ldloc.0
0x12e11  ldstr    aServiceinstanc// "ServiceInstance"
0x12e16  ldarg.0
0x12e17  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Services.ServiceInstance::get_Id()
0x12e1c  box      [mscorlib]System.Guid
0x12e21  ldloc.1
0x12e22  ldc.i4   0x10C
0x12e27  ldstr    aSetserviceinst// "SetServiceInstance"
0x12e2c  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x12e31  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x12e36  stloc.2
0x12e37  ldloc.2
0x12e38  brtrue.s loc_12E51
0x12e3a  ldarg.0
0x12e3b  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.Puid Microsoft.Crm.CrmLive.Services.ServiceInstance::get_UserPuid()
0x12e40  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.Puid::get_Text()
0x12e45  ldarg.0
0x12e46  callvirt instance string Microsoft.Crm.CrmLive.Services.ServiceInstance::get_ServiceInstanceId()
0x12e4b  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.CrmLive.Services.ServiceInstanceService::TryGetServiceInstance(string puid, string serviceInstanceId)
0x12e50  stloc.2
0x12e51  ldloc.2
0x12e52  brtrue.s loc_12E60
0x12e54  ldarg.0
0x12e55  callvirt instance string Microsoft.Crm.CrmLive.Services.ServiceInstance::get_ServiceInstanceId()
0x12e5a  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.CrmLive.Services.ServiceInstanceService::TryGetServiceInstanceMatchesSku(string serviceInstanceId)
0x12e5f  stloc.2
0x12e60  ldloc.2
0x12e61  brtrue   loc_12F33
0x12e66  ldarg.0
0x12e67  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Services.ServiceInstance::get_Id()
0x12e6c  stloc.3
0x12e6d  ldloc.3
0x12e6e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x12e73  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x12e78  brfalse.s loc_12E80
0x12e7a  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x12e7f  stloc.3
0x12e80  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x12e85  stloc.s  4
0x12e87  ldloc.s  4
0x12e89  ldstr    aFriendlyname// "FriendlyName"
0x12e8e  ldarg.0
0x12e8f  callvirt instance string Microsoft.Crm.CrmLive.Services.ServiceInstance::get_ServiceInstanceFriendlyName()
0x12e94  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12e99  ldloc.s  4
0x12e9b  ldstr    aId// "Id"
0x12ea0  ldloc.3
0x12ea1  box      [mscorlib]System.Guid
0x12ea6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12eab  ldloc.s  4
0x12ead  ldstr    aOrganizationid_0// "OrganizationId"
0x12eb2  ldarg.0
0x12eb3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Services.ServiceInstance::get_OrganizationId()
0x12eb8  box      [mscorlib]System.Guid
0x12ebd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12ec2  ldloc.s  4
0x12ec4  ldstr    aPuid_0// "Puid"
0x12ec9  ldarg.0
0x12eca  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.Puid Microsoft.Crm.CrmLive.Services.ServiceInstance::get_UserPuid()
0x12ecf  callvirt instance string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.Puid::get_Text()
0x12ed4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12ed9  ldloc.s  4
0x12edb  ldstr    aServicecompone// "ServiceComponentId"
0x12ee0  ldarg.0
0x12ee1  callvirt instance string Microsoft.Crm.CrmLive.Services.ServiceInstance::get_ServiceComponentId()
0x12ee6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12eeb  ldloc.s  4
0x12eed  ldstr    aServiceinstanc_0// "ServiceInstanceId"
0x12ef2  ldarg.0
0x12ef3  callvirt instance string Microsoft.Crm.CrmLive.Services.ServiceInstance::get_ServiceInstanceId()
0x12ef8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12efd  ldloc.s  4
0x12eff  ldstr    aStatuscode// "StatusCode"
0x12f04  ldarg.0
0x12f05  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ServiceInstanceStatus Microsoft.Crm.CrmLive.Services.ServiceInstance::get_ServiceInstanceStatus()
0x12f0a  box      [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ServiceInstanceStatus
0x12f0f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12f14  ldloc.0
0x12f15  ldstr    aServiceinstanc// "ServiceInstance"
0x12f1a  ldloc.s  4
0x12f1c  ldc.i4   0x12F
0x12f21  ldstr    aSetserviceinst// "SetServiceInstance"
0x12f26  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x12f2b  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x12f30  pop
0x12f31  leave.s  loc_12F97
0x12f33  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x12f38  stloc.s  5
0x12f3a  ldloc.s  5
0x12f3c  ldstr    aStatuscode// "StatusCode"
0x12f41  ldarg.0
0x12f42  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ServiceInstanceStatus Microsoft.Crm.CrmLive.Services.ServiceInstance::get_ServiceInstanceStatus()
0x12f47  box      [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ServiceInstanceStatus
0x12f4c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12f51  ldloc.s  5
0x12f53  ldstr    aServicecompone// "ServiceComponentId"
0x12f58  ldarg.0
0x12f59  callvirt instance string Microsoft.Crm.CrmLive.Services.ServiceInstance::get_ServiceComponentId()
0x12f5e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x12f63  ldloc.0
0x12f64  ldstr    aServiceinstanc// "ServiceInstance"
0x12f69  ldloc.2
0x12f6a  ldstr    aId// "Id"
0x12f6f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x12f74  ldloc.s  5
0x12f76  ldc.i4   0x138
0x12f7b  ldstr    aSetserviceinst// "SetServiceInstance"
0x12f80  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x12f85  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x12f8a  pop
0x12f8b  leave.s  loc_12F97
0x12f8d  ldloc.0
0x12f8e  brfalse.s loc_12F96
0x12f90  ldloc.0
0x12f91  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12f96  endfinally
0x12f97  ret
```
