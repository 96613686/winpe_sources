# Microsoft.Crm.CrmLive.Provisioning.SyncUserCreateHandler::GetDefaultSecurityRolesSetting

- ea: `0x10c80`
- end: `0x10d66`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncUserCreateHandler::GetDefaultSecurityRolesSetting`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x10b40`

## callees

- `0x10c80`

## string_xrefs

- `0x10cd8`: `DefaultSecurityRoles`
- `0x10cfe`: `DefaultSecurityRoles`
- `0x10ce4`: `GetDefaultSecurityRolesSetting`
- `0x10ce9`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SyncData\UserHandler\SyncUserCreateHandler.cs`

## pseudocode

```c

```

## disassembly

```asm
0x10c80  ldstr    aDefsecrole// "DefSecRole:"
0x10c85  ldarg.0
0x10c86  box      [mscorlib]System.Guid
0x10c8b  call     string [mscorlib]System.String::Concat(object, object)
0x10c90  stloc.0
0x10c91  ldsfld   class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache Microsoft.Crm.CrmLive.Provisioning.SyncUserCreateHandler::_cache
0x10c96  ldloc.0
0x10c97  ldnull
0x10c98  callvirt instance class [System.Runtime.Caching]System.Runtime.Caching.CacheItem [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::GetCacheItem(string, string)
0x10c9d  stloc.1
0x10c9e  ldloc.1
0x10c9f  brfalse.s loc_10CAD
0x10ca1  ldloc.1
0x10ca2  callvirt instance object [System.Runtime.Caching]System.Runtime.Caching.CacheItem::get_Value()
0x10ca7  castclass [mscorlib]System.String
0x10cac  ret
0x10cad  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x10cb2  stloc.2
0x10cb3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x10cb8  stloc.3
0x10cb9  ldloc.3
0x10cba  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x10cbf  ldarg.0
0x10cc0  box      [mscorlib]System.Guid
0x10cc5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x10cca  ldloc.2
0x10ccb  ldstr    aOrganizationli// "OrganizationLifecycle"
0x10cd0  ldc.i4.1
0x10cd1  newarr   [mscorlib]System.String
0x10cd6  dup
0x10cd7  ldc.i4.0
0x10cd8  ldstr    aDefaultsecurit// "DefaultSecurityRoles"
0x10cdd  stelem.ref
0x10cde  ldloc.3
0x10cdf  ldc.i4   0x8C
0x10ce4  ldstr    aGetdefaultsecu// "GetDefaultSecurityRolesSetting"
0x10ce9  ldstr    aDDbsShDccm2110_22// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x10cee  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x10cf3  stloc.s  4
0x10cf5  ldnull
0x10cf6  stloc.s  5
0x10cf8  ldloc.s  4
0x10cfa  brfalse.s loc_10D0F
0x10cfc  ldloc.s  4
0x10cfe  ldstr    aDefaultsecurit// "DefaultSecurityRoles"
0x10d03  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x10d08  castclass [mscorlib]System.String
0x10d0d  stloc.s  5
0x10d0f  ldloc.s  5
0x10d11  brtrue.s loc_10D1A
0x10d13  ldsfld   string [mscorlib]System.String::Empty
0x10d18  stloc.s  5
0x10d1a  ldsfld   class [System.Runtime.Caching]System.Runtime.Caching.MemoryCache Microsoft.Crm.CrmLive.Provisioning.SyncUserCreateHandler::_cache
0x10d1f  ldloc.0
0x10d20  ldloc.s  5
0x10d22  newobj   instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItem::.ctor(string, object)
0x10d27  newobj   instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy::.ctor()
0x10d2c  dup
0x10d2d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x10d32  stloc.s  6
0x10d34  ldloca.s 6
0x10d36  ldc.r8   1.0
0x10d3f  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x10d44  call     valuetype [mscorlib]System.DateTimeOffset [mscorlib]System.DateTimeOffset::op_Implicit(valuetype [mscorlib]System.DateTime)
0x10d49  callvirt instance void [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy::set_AbsoluteExpiration(valuetype [mscorlib]System.DateTimeOffset)
0x10d4e  callvirt instance void [System.Runtime.Caching]System.Runtime.Caching.ObjectCache::Set(class [System.Runtime.Caching]System.Runtime.Caching.CacheItem, class [System.Runtime.Caching]System.Runtime.Caching.CacheItemPolicy)
0x10d53  ldloc.s  5
0x10d55  stloc.s  7
0x10d57  leave.s  loc_10D63
0x10d59  ldloc.2
0x10d5a  brfalse.s loc_10D62
0x10d5c  ldloc.2
0x10d5d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10d62  endfinally
0x10d63  ldloc.s  7
0x10d65  ret
```
