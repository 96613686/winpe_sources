# Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::BuildInfo

- ea: `0x510`
- end: `0x6f0`
- name: `Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::BuildInfo`
- size: `480`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x400`
- `0x420`
- `0x430`
- `0x440`
- `0x450`
- `0x490`
- `0x4a0`
- `0x510`
- `0x6f0`
- `0x790`
- `0x860`

## string_xrefs

- `0x558`: `AppIdUri`
- `0x590`: `AppIdUri`
- `0x5dc`: `AppIdUri`
- `0x5a8`: `AllowedAdditionalAzureAdAppInfo`
- `0x60f`: `AllowedAdditionalAzureAdAppInfo`
- `0x61d`: `AllowedAdditionalAzureAdAppInfo`

## pseudocode

```c

```

## disassembly

```asm
0x510  newobj   instance void Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::.ctor()
0x515  stloc.0
0x516  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x51b  stloc.1
0x51c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x521  stloc.2
0x522  ldloc.2
0x523  ldstr    aType// "Type"
0x528  ldc.i4.2
0x529  box      [mscorlib]System.Int32
0x52e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x533  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x538  stloc.3
0x539  ldloc.3
0x53a  ldstr    aType// "Type"
0x53f  ldc.i4.1
0x540  box      [mscorlib]System.Int32
0x545  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x54a  ldloc.1
0x54b  ldstr    aAzureapplicati// "AzureApplication"
0x550  ldc.i4.3
0x551  newarr   [mscorlib]System.String
0x556  dup
0x557  ldc.i4.0
0x558  ldstr    aAppiduri// "AppIdUri"
0x55d  stelem.ref
0x55e  dup
0x55f  ldc.i4.1
0x560  ldstr    aClientid// "ClientId"
0x565  stelem.ref
0x566  dup
0x567  ldc.i4.2
0x568  ldstr    aDomain// "Domain"
0x56d  stelem.ref
0x56e  ldloc.2
0x56f  ldc.i4.s 0x45
0x571  ldstr    aBuildinfo// "BuildInfo"
0x576  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x57b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x580  stloc.s  4
0x582  ldloc.1
0x583  ldstr    aAzureapplicati// "AzureApplication"
0x588  ldc.i4.4
0x589  newarr   [mscorlib]System.String
0x58e  dup
0x58f  ldc.i4.0
0x590  ldstr    aAppiduri// "AppIdUri"
0x595  stelem.ref
0x596  dup
0x597  ldc.i4.1
0x598  ldstr    aClientid// "ClientId"
0x59d  stelem.ref
0x59e  dup
0x59f  ldc.i4.2
0x5a0  ldstr    aDomain// "Domain"
0x5a5  stelem.ref
0x5a6  dup
0x5a7  ldc.i4.3
0x5a8  ldstr    aAllowedadditio// "AllowedAdditionalAzureAdAppInfo"
0x5ad  stelem.ref
0x5ae  ldloc.3
0x5af  ldc.i4.s 0x46
0x5b1  ldstr    aBuildinfo// "BuildInfo"
0x5b6  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x5bb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x5c0  stloc.s  5
0x5c2  ldloc.0
0x5c3  ldloc.s  5
0x5c5  ldstr    aDomain// "Domain"
0x5ca  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5cf  castclass [mscorlib]System.String
0x5d4  callvirt instance void Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::set_ScaleGroupApiDomain(string value)
0x5d9  ldloc.0
0x5da  ldloc.s  5
0x5dc  ldstr    aAppiduri// "AppIdUri"
0x5e1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5e6  castclass [mscorlib]System.String
0x5eb  callvirt instance void Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::set_ScaleGroupAppIdUri(string value)
0x5f0  ldloc.0
0x5f1  ldloc.s  4
0x5f3  ldstr    aClientid// "ClientId"
0x5f8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5fd  unbox.any [mscorlib]System.Guid
0x602  callvirt instance void Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::set_SiteApiClientId(valuetype [mscorlib]System.Guid value)
0x607  ldloc.0
0x608  call     void Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::SetSiteAppDomainTenantId(class Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo info)
0x60d  ldloc.s  5
0x60f  ldstr    aAllowedadditio// "AllowedAdditionalAzureAdAppInfo"
0x614  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x619  brfalse.s loc_63B
0x61b  ldloc.s  5
0x61d  ldstr    aAllowedadditio// "AllowedAdditionalAzureAdAppInfo"
0x622  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x627  castclass [mscorlib]System.String
0x62c  stloc.s  6
0x62e  ldloc.0
0x62f  ldloc.s  6
0x631  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::GetAllowedTenantAndClientIds(string tenantAndClientIds)
0x636  callvirt instance void Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::set_AllowedTenantAndClientIds(class [mscorlib]System.Collections.Generic.List`1<string> value)
0x63b  ldloc.0
0x63c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::get_AllowedTenantAndClientIds()
0x641  brtrue.s loc_64E
0x643  ldloc.0
0x644  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x649  callvirt instance void Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::set_AllowedTenantAndClientIds(class [mscorlib]System.Collections.Generic.List`1<string> value)
0x64e  ldloc.0
0x64f  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::get_AllowedTenantAndClientIds()
0x654  ldloc.0
0x655  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::get_TenantId()
0x65a  stloc.s  7
0x65c  ldloca.s 7
0x65e  constrained. [mscorlib]System.Guid
0x664  callvirt instance string [mscorlib]System.Object::ToString()
0x669  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x66e  ldstr    asc_652E// ":"
0x673  ldloc.0
0x674  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::get_SiteApiClientId()
0x679  stloc.s  7
0x67b  ldloca.s 7
0x67d  constrained. [mscorlib]System.Guid
0x683  callvirt instance string [mscorlib]System.Object::ToString()
0x688  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x68d  call     string [mscorlib]System.String::Concat(string, string, string)
0x692  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x697  brtrue.s loc_6E2
0x699  ldloc.0
0x69a  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::get_AllowedTenantAndClientIds()
0x69f  ldloc.0
0x6a0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::get_TenantId()
0x6a5  stloc.s  7
0x6a7  ldloca.s 7
0x6a9  constrained. [mscorlib]System.Guid
0x6af  callvirt instance string [mscorlib]System.Object::ToString()
0x6b4  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x6b9  ldstr    asc_652E// ":"
0x6be  ldloc.0
0x6bf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::get_SiteApiClientId()
0x6c4  stloc.s  7
0x6c6  ldloca.s 7
0x6c8  constrained. [mscorlib]System.Guid
0x6ce  callvirt instance string [mscorlib]System.Object::ToString()
0x6d3  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x6d8  call     string [mscorlib]System.String::Concat(string, string, string)
0x6dd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6e2  leave.s  loc_6EE
0x6e4  ldloc.1
0x6e5  brfalse.s loc_6ED
0x6e7  ldloc.1
0x6e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6ed  endfinally
0x6ee  ldloc.0
0x6ef  ret
```
