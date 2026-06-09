# Microsoft.Crm.Metadata.OrganizationBaseLanguageCache::.ctor

- ea: `0x4c750`
- end: `0x4c7a2`
- name: `Microsoft.Crm.Metadata.OrganizationBaseLanguageCache::.ctor`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4c880`

## callees

- `0x4c750`

## string_xrefs

- `0x4c751`: `OrganizationBaseLanguageCache`
- `0x4c781`: `Microsoft.Crm.Application.Components.Platform`
- `0x4c786`: `Microsoft.Crm.Caching.OrganizationBaseLanguageClientCacheLoader`
- `0x4c797`: `Microsoft.Crm.Caching.OrganizationBaseLanguageCacheLoader`

## pseudocode

```c

```

## disassembly

```asm
0x4c750  ldarg.0
0x4c751  ldstr    aOrganizationba// "OrganizationBaseLanguageCache"
0x4c756  ldc.i4.3
0x4c757  newarr   [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType
0x4c75c  dup
0x4c75d  ldtoken  valuetype __StaticArrayInitTypeSize=12 <PrivateImplementationDetails>::E040BD11F61A2757434127A9CAD036853C1EFEAA
0x4c762  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x4c767  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::MaxValue
0x4c76c  ldc.i4.0
0x4c76d  call     instance void class Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, int32>::.ctor(string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType[], valuetype [mscorlib]System.TimeSpan, bool)
0x4c772  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x4c777  brfalse.s loc_4C791
0x4c779  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x4c77e  brtrue.s loc_4C791
0x4c780  ldarg.0
0x4c781  ldstr    aMicrosoftCrmAp// "Microsoft.Crm.Application.Components.Pl"...
0x4c786  ldstr    aMicrosoftCrmCa_0// "Microsoft.Crm.Caching.OrganizationBaseL"...
0x4c78b  call     instance void class Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, int32>::SetLoader(string, string)
0x4c790  ret
0x4c791  ldarg.0
0x4c792  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x4c797  ldstr    aMicrosoftCrmCa_1// "Microsoft.Crm.Caching.OrganizationBaseL"...
0x4c79c  call     instance void class Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, int32>::SetLoader(string, string)
0x4c7a1  ret
```
