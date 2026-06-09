# Microsoft.Crm.CrmLive.Provisioning.CapabilityRoleInfoCacheableService::GetCapabilityUserRoles

- ea: `0xbb40`
- end: `0xbc2d`
- name: `Microsoft.Crm.CrmLive.Provisioning.CapabilityRoleInfoCacheableService::GetCapabilityUserRoles`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0xbb40`
- `0x1c350`
- `0x2e900`
- `0x2ea90`
- `0x2eac0`

## string_xrefs

- `0xbb40`: `CapabilityRoleInfoCacheableService_{0}_{1}`

## pseudocode

```c

```

## disassembly

```asm
0xbb40  ldstr    aCapabilityrole_0// "CapabilityRoleInfoCacheableService_{0}_"...
0xbb45  ldarga.s 1
0xbb47  constrained. [mscorlib]System.Guid
0xbb4d  callvirt instance string [mscorlib]System.Object::ToString()
0xbb52  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xbb57  ldarga.s 2
0xbb59  constrained. [mscorlib]System.Guid
0xbb5f  callvirt instance string [mscorlib]System.Object::ToString()
0xbb64  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xbb69  call     string [mscorlib]System.String::Format(string, object, object)
0xbb6e  stloc.0
0xbb6f  call     class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache [System.Runtime.Caching]System.Runtime.Caching.MemoryCache::get_Default()
0xbb74  ldloc.0
0xbb75  ldnull
0xbb76  callvirt instance object [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::Get(string, string)
0xbb7b  isinst   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xbb80  stloc.1
0xbb81  ldarg.0
0xbb82  ldfld    class Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess Microsoft.Crm.CrmLive.Provisioning.CapabilityRoleInfoCacheableService::_orgAccess
0xbb87  ldarg.1
0xbb88  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.IOrganizationDatabaseAccess::GetRoleCount(valuetype [mscorlib]System.Guid organizationId)
0xbb8d  stloc.2
0xbb8e  ldloc.1
0xbb8f  brfalse.s loc_BBC1
0xbb91  ldloc.1
0xbb92  ldstr    aRolecount// "RoleCount"
0xbb97  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xbb9c  unbox.any [mscorlib]System.Int32
0xbba1  ldloc.2
0xbba2  bne.un.s loc_BBC1
0xbba4  call     class Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentEventSource Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentEventSource::get_Instance()
0xbba9  ldarg.1
0xbbaa  ldarg.2
0xbbab  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentEventSource::GetCapabilityUserRolesCacheHit(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid businessUnitId)
0xbbb0  ldloc.1
0xbbb1  ldstr    aCapabilityuser// "CapabilityUserRoles"
0xbbb6  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xbbbb  isinst   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid>>
0xbbc0  ret
0xbbc1  call     class Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentEventSource Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentEventSource::get_Instance()
0xbbc6  ldarg.1
0xbbc7  ldarg.2
0xbbc8  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.LicenseBasedRoleAssignmentEventSource::GetCapabilityUserRolesCacheMiss(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid businessUnitId)
0xbbcd  ldarg.3
0xbbce  callvirt instance var<u1> class [mscorlib]System.Func`1<class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid>>>::Invoke()
0xbbd3  stloc.3
0xbbd4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xbbd9  stloc.1
0xbbda  ldloc.1
0xbbdb  ldstr    aRolecount// "RoleCount"
0xbbe0  ldloc.2
0xbbe1  box      [mscorlib]System.Int32
0xbbe6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xbbeb  ldloc.1
0xbbec  ldstr    aCapabilityuser// "CapabilityUserRoles"
0xbbf1  ldloc.3
0xbbf2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xbbf7  call     class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache [System.Runtime.Caching]System.Runtime.Caching.MemoryCache::get_Default()
0xbbfc  ldloc.0
0xbbfd  ldloc.1
0xbbfe  newobj   instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy::.ctor()
0xbc03  dup
0xbc04  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xbc09  stloc.s  4
0xbc0b  ldloca.s 4
0xbc0d  ldc.r8   15.0
0xbc16  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0xbc1b  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0xbc20  callvirt instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy::set_AbsoluteExpiration(valuetype [mscorlib]System.DateTimeOffset)
0xbc25  ldnull
0xbc26  callvirt instance void [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::Set(string, object, class [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy, string)
0xbc2b  ldloc.3
0xbc2c  ret
```
