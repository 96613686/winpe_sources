# Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::TrySaveEmailAndUserId

- ea: `0x5c0`
- end: `0x6d9`
- name: `Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::TrySaveEmailAndUserId`
- size: `281`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x580`

## callees

- `0x5c0`

## pseudocode

```c

```

## disassembly

```asm
0x5c0  ldc.i4.5
0x5c1  newarr   [mscorlib]System.String
0x5c6  dup
0x5c7  ldc.i4.0
0x5c8  ldstr    aWindowsliveid// "windowsliveid"
0x5cd  stelem.ref
0x5ce  dup
0x5cf  ldc.i4.1
0x5d0  ldstr    aInternalemaila// "internalemailaddress"
0x5d5  stelem.ref
0x5d6  dup
0x5d7  ldc.i4.2
0x5d8  ldstr    aPersonalemaila// "personalemailaddress"
0x5dd  stelem.ref
0x5de  dup
0x5df  ldc.i4.3
0x5e0  ldstr    aMobilealertema// "mobilealertemail"
0x5e5  stelem.ref
0x5e6  dup
0x5e7  ldc.i4.4
0x5e8  ldstr    aYammeruserid// "yammeruserid"
0x5ed  stelem.ref
0x5ee  stloc.0
0x5ef  ldstr    aSystemuser// "systemuser"
0x5f4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5f9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x5fe  ldloc.0
0x5ff  ldc.i4.0
0x600  ldc.i4.1
0x601  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x606  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], bool, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x60b  stloc.1
0x60c  ldloc.1
0x60d  ldstr    aYammeruserid// "yammeruserid"
0x612  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x617  isinst   [mscorlib]System.String
0x61c  stloc.2
0x61d  ldloc.2
0x61e  brfalse.s loc_62C
0x620  ldloc.2
0x621  ldarg.1
0x622  ldc.i4.5
0x623  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x628  brfalse.s loc_62C
0x62a  ldc.i4.1
0x62b  ret
0x62c  ldloc.0
0x62d  stloc.3
0x62e  ldc.i4.0
0x62f  stloc.s  4
0x631  br       loc_6CD
0x636  ldloc.3
0x637  ldloc.s  4
0x639  ldelem.ref
0x63a  stloc.s  5
0x63c  ldloc.1
0x63d  ldloc.s  5
0x63f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x644  isinst   [mscorlib]System.String
0x649  stloc.s  6
0x64b  ldloc.s  6
0x64d  brfalse.s loc_6C7
0x64f  ldarg.0
0x650  ldloc.s  6
0x652  ldc.i4.5
0x653  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x658  brfalse.s loc_6C7
0x65a  ldstr    aSystemuser// "systemuser"
0x65f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x664  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x669  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x66e  dup
0x66f  ldstr    aSystemuserid// "systemuserid"
0x674  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x679  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x67e  box      [mscorlib]System.Guid
0x683  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x688  dup
0x689  ldstr    aYammeremailadd// "yammeremailaddress"
0x68e  ldarg.0
0x68f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x694  dup
0x695  ldstr    aYammeruserid// "yammeruserid"
0x69a  ldarg.1
0x69b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x6a0  ldc.i4.1
0x6a1  ldc.i4.0
0x6a2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6a7  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, bool, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6ac  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x6b1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6b6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x6bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6c0  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::RemoveEntry(var<u1>, !!T0)
0x6c5  ldc.i4.1
0x6c6  ret
0x6c7  ldloc.s  4
0x6c9  ldc.i4.1
0x6ca  add
0x6cb  stloc.s  4
0x6cd  ldloc.s  4
0x6cf  ldloc.3
0x6d0  ldlen
0x6d1  conv.i4
0x6d2  blt      loc_636
0x6d7  ldc.i4.0
0x6d8  ret
```
