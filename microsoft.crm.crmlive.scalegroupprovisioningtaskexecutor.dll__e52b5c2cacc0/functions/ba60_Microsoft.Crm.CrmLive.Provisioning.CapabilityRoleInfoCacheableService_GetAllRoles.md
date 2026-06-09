# Microsoft.Crm.CrmLive.Provisioning.CapabilityRoleInfoCacheableService::GetAllRoles

- ea: `0xba60`
- end: `0xbb39`
- name: `Microsoft.Crm.CrmLive.Provisioning.CapabilityRoleInfoCacheableService::GetAllRoles`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0xba60`
- `0x1c350`
- `0x2e900`
- `0x2ea50`
- `0x2ea70`

## string_xrefs

- `0xba60`: `CapabilityRoleInfoCacheableService_`

## pseudocode

```c

```

## disassembly

```asm
0xba60  ldstr    aCapabilityrole// "CapabilityRoleInfoCacheableService_"
0xba65  ldarga.s 1
0xba67  constrained. [mscorlib]System.Guid
0xba6d  callvirt instance string [mscorlib]System.Object::ToString()
0xba72  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xba77  call     string [mscorlib]System.String::Concat(string, string)
0xba7c  stloc.0
0xba7d  call     class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache [System.Runtime.Caching]System.Runtime.Caching.MemoryCache::get_Default()
0xba82  ldloc.0
0xba83  ldnull
0xba84  callvirt instance object [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::Get(string, string)
0xba89  isinst   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xba8e  stloc.1
0xba8f  ldarg.0
0xba90  ldfld    class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.CapabilityRoleInfoCacheableService::_orgAccess
0xba95  ldarg.1
0xba96  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::GetRoleCount(valuetype [mscorlib]System.Guid organizationId)
0xba9b  stloc.2
0xba9c  ldloc.1
0xba9d  brfalse.s loc_BACE
0xba9f  ldloc.1
0xbaa0  ldstr    aRolecount// "RoleCount"
0xbaa5  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xbaaa  unbox.any [mscorlib]System.Int32
0xbaaf  ldloc.2
0xbab0  bne.un.s loc_BACE
0xbab2  call     class Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentEventSource Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentEventSource::get_Instance()
0xbab7  ldarg.1
0xbab8  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentEventSource::GetAllRolesCacheHit(valuetype [mscorlib]System.Guid organizationId)
0xbabd  ldloc.1
0xbabe  ldstr    aRoles// "Roles"
0xbac3  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xbac8  isinst   class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0xbacd  ret
0xbace  call     class Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentEventSource Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentEventSource::get_Instance()
0xbad3  ldarg.1
0xbad4  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentEventSource::GetAllRolesCacheMiss(valuetype [mscorlib]System.Guid organizationId)
0xbad9  ldarg.2
0xbada  callvirt instance var<u1> class [mscorlib]System.Func`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>>::Invoke()
0xbadf  stloc.3
0xbae0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xbae5  stloc.1
0xbae6  ldloc.1
0xbae7  ldstr    aRolecount// "RoleCount"
0xbaec  ldloc.2
0xbaed  box      [mscorlib]System.Int32
0xbaf2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xbaf7  ldloc.1
0xbaf8  ldstr    aRoles// "Roles"
0xbafd  ldloc.3
0xbafe  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xbb03  call     class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache [System.Runtime.Caching]System.Runtime.Caching.MemoryCache::get_Default()
0xbb08  ldloc.0
0xbb09  ldloc.1
0xbb0a  newobj   instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy::.ctor()
0xbb0f  dup
0xbb10  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xbb15  stloc.s  4
0xbb17  ldloca.s 4
0xbb19  ldc.r8   15.0
0xbb22  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0xbb27  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0xbb2c  callvirt instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy::set_AbsoluteExpiration(valuetype [mscorlib]System.DateTimeOffset)
0xbb31  ldnull
0xbb32  callvirt instance void [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::Set(string, object, class [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy, string)
0xbb37  ldloc.3
0xbb38  ret
```
