# Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeWithMinimumPrivilegeDepth

- ea: `0x625d0`
- end: `0x62635`
- name: `Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeWithMinimumPrivilegeDepth`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x620b0`
- `0x625d0`
- `0x64410`
- `0x66b10`

## string_xrefs

- `0x625e7`: `privilege`
- `0x62611`: `userCache`

## pseudocode

```c

```

## disassembly

```asm
0x625d0  ldarg.0
0x625d1  ldstr    aObjectbusiness// "objectBusinessUnitId"
0x625d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x625db  ldarg.1
0x625dc  ldstr    aMetadata_0// "metadata"
0x625e1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x625e6  ldarg.2
0x625e7  ldstr    aPrivilege_0// "privilege"
0x625ec  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x625f1  ldarg.3
0x625f2  ldstr    aContext// "context"
0x625f7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x625fc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x62601  ldarg.3
0x62602  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x62607  ldarg.3
0x62608  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x6260d  stloc.0
0x6260e  ldloc.0
0x6260f  brtrue.s loc_6261C
0x62611  ldstr    aUsercache// "userCache"
0x62616  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x6261b  throw
0x6261c  ldarg.1
0x6261d  ldloc.0
0x6261e  ldarg.0
0x6261f  ldarg.3
0x62620  call     int32 Microsoft.Crm.BusinessEntities.SecurityLibrary::DetermineMinimumPrivilegeDepth(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal userOrTeam, valuetype [mscorlib]System.Guid objectBusinessId, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x62625  stloc.1
0x62626  ldarg.3
0x62627  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x6262c  ldarg.2
0x6262d  ldloc.1
0x6262e  ldarg.3
0x6262f  call     void Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilege(valuetype [mscorlib]System.Guid user, valuetype [mscorlib]System.Guid privilege, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth requiredDepth, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x62634  ret
```
