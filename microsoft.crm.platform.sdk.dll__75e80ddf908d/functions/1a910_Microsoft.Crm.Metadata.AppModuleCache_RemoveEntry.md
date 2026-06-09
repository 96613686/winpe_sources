# Microsoft.Crm.Metadata.AppModuleCache::RemoveEntry

- ea: `0x1a910`
- end: `0x1ac77`
- name: `Microsoft.Crm.Metadata.AppModuleCache::RemoveEntry`
- size: `871`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1b830`

## callees

- `0x1a540`
- `0x1a5e0`
- `0x1a600`
- `0x1a910`

## string_xrefs

- `0x1a918`: `AppModuleCache.RemoveEntry(): Request to remove AppModule with [appmoduleid:{0}] or [url:{1}] from cache.`
- `0x1a9da`: `AppModuleCache.RemoveEntry(): Removed [appmoduleid:{0}],[url:{1}] from cache.`
- `0x1aafa`: `AppModuleCache.RemoveEntry(): Removed [appmoduleid:{0}],[url:{1}] from cache.`
- `0x1ac1d`: `AppModuleCache.RemoveEntry(): Removed [appmoduleid:{0}],[url:{1}] from cache.`
- `0x1aa09`: `Removed AppModule {0} from AppModuleCache`
- `0x1ab2b`: `Removed AppModule {0} from AppModuleCache`
- `0x1ac4e`: `Removed AppModule {0} from AppModuleCache`

## pseudocode

```c

```

## disassembly

```asm
0x1a910  ldarg.2
0x1a911  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1a916  ldc.i4.s 0x47
0x1a918  ldstr    aAppmodulecache_1// "AppModuleCache.RemoveEntry(): Request t"...
0x1a91d  ldc.i4.2
0x1a91e  newarr   [mscorlib]System.Object
0x1a923  dup
0x1a924  ldc.i4.0
0x1a925  ldarg.1
0x1a926  stelem.ref
0x1a927  dup
0x1a928  ldc.i4.1
0x1a929  ldarg.1
0x1a92a  stelem.ref
0x1a92b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1a930  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a935  stloc.0
0x1a936  ldarg.1
0x1a937  ldloca.s 0
0x1a939  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x1a93e  brfalse  loc_1AA31
0x1a943  ldarg.0
0x1a944  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheById
0x1a949  ldarg.1
0x1a94a  ldarg.2
0x1a94b  callvirt instance bool class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::ContainsKey(var<u1>, !!T0)
0x1a950  brfalse  loc_1AA31
0x1a955  ldarg.0
0x1a956  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheById
0x1a95b  ldarg.1
0x1a95c  ldarg.2
0x1a95d  callvirt instance var<u1> class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::LookupEntry(void, var<u1>)
0x1a962  stloc.1
0x1a963  ldarg.2
0x1a964  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1a969  stloc.3
0x1a96a  ldloca.s 3
0x1a96c  constrained. [mscorlib]System.Guid
0x1a972  callvirt instance string [mscorlib]System.Object::ToString()
0x1a977  ldstr    asc_C09D0// "_"
0x1a97c  ldloc.1
0x1a97d  callvirt instance string Microsoft.Crm.Metadata.AppModuleMetadata::get_Url()
0x1a982  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a987  stloc.2
0x1a988  ldarg.0
0x1a989  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheByUrl
0x1a98e  ldloc.2
0x1a98f  ldarg.2
0x1a990  callvirt instance void class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::RemoveEntry(var<u1>, !!T0)
0x1a995  ldarg.0
0x1a996  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheById
0x1a99b  ldarg.1
0x1a99c  ldarg.2
0x1a99d  callvirt instance void class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::RemoveEntry(var<u1>, !!T0)
0x1a9a2  ldarg.0
0x1a9a3  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheByUName
0x1a9a8  ldarg.2
0x1a9a9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1a9ae  stloc.3
0x1a9af  ldloca.s 3
0x1a9b1  constrained. [mscorlib]System.Guid
0x1a9b7  callvirt instance string [mscorlib]System.Object::ToString()
0x1a9bc  ldstr    asc_C09D0// "_"
0x1a9c1  ldloc.1
0x1a9c2  callvirt instance string Microsoft.Crm.Metadata.AppModuleMetadata::get_UniqueName()
0x1a9c7  call     string [mscorlib]System.String::Concat(string, string, string)
0x1a9cc  ldarg.2
0x1a9cd  callvirt instance void class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::RemoveEntry(var<u1>, !!T0)
0x1a9d2  ldarg.2
0x1a9d3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1a9d8  ldc.i4.s 0x47
0x1a9da  ldstr    aAppmodulecache_2// "AppModuleCache.RemoveEntry(): Removed ["...
0x1a9df  ldc.i4.2
0x1a9e0  newarr   [mscorlib]System.Object
0x1a9e5  dup
0x1a9e6  ldc.i4.0
0x1a9e7  ldloc.1
0x1a9e8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AppModuleMetadata::get_AppModuleId()
0x1a9ed  box      [mscorlib]System.Guid
0x1a9f2  stelem.ref
0x1a9f3  dup
0x1a9f4  ldc.i4.1
0x1a9f5  ldloc.1
0x1a9f6  callvirt instance string Microsoft.Crm.Metadata.AppModuleMetadata::get_Url()
0x1a9fb  stelem.ref
0x1a9fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1aa01  ldarg.2
0x1aa02  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1aa07  ldc.i4.s 0x14
0x1aa09  ldstr    aRemovedAppmodu// "Removed AppModule {0} from AppModuleCac"...
0x1aa0e  ldc.i4.1
0x1aa0f  newarr   [mscorlib]System.Object
0x1aa14  dup
0x1aa15  ldc.i4.0
0x1aa16  ldloc.1
0x1aa17  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AppModuleMetadata::get_AppModuleId()
0x1aa1c  stloc.3
0x1aa1d  ldloca.s 3
0x1aa1f  constrained. [mscorlib]System.Guid
0x1aa25  callvirt instance string [mscorlib]System.Object::ToString()
0x1aa2a  stelem.ref
0x1aa2b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1aa30  ret
0x1aa31  ldarg.0
0x1aa32  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheByUrl
0x1aa37  ldarg.2
0x1aa38  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1aa3d  stloc.3
0x1aa3e  ldloca.s 3
0x1aa40  constrained. [mscorlib]System.Guid
0x1aa46  callvirt instance string [mscorlib]System.Object::ToString()
0x1aa4b  ldstr    asc_C09D0// "_"
0x1aa50  ldarg.1
0x1aa51  call     string [mscorlib]System.String::Concat(string, string, string)
0x1aa56  ldarg.2
0x1aa57  callvirt instance bool class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::ContainsKey(var<u1>, !!T0)
0x1aa5c  brfalse  loc_1AB54
0x1aa61  ldarg.2
0x1aa62  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1aa67  stloc.3
0x1aa68  ldloca.s 3
0x1aa6a  constrained. [mscorlib]System.Guid
0x1aa70  callvirt instance string [mscorlib]System.Object::ToString()
0x1aa75  ldstr    asc_C09D0// "_"
0x1aa7a  ldarg.1
0x1aa7b  call     string [mscorlib]System.String::Concat(string, string, string)
0x1aa80  stloc.s  4
0x1aa82  ldarg.0
0x1aa83  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheByUrl
0x1aa88  ldloc.s  4
0x1aa8a  ldarg.2
0x1aa8b  callvirt instance var<u1> class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::LookupEntry(void, var<u1>)
0x1aa90  stloc.s  5
0x1aa92  ldarg.0
0x1aa93  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheById
0x1aa98  ldloc.s  5
0x1aa9a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AppModuleMetadata::get_AppModuleId()
0x1aa9f  stloc.3
0x1aaa0  ldloca.s 3
0x1aaa2  constrained. [mscorlib]System.Guid
0x1aaa8  callvirt instance string [mscorlib]System.Object::ToString()
0x1aaad  ldarg.2
0x1aaae  callvirt instance void class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::RemoveEntry(var<u1>, !!T0)
0x1aab3  ldarg.0
0x1aab4  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheByUrl
0x1aab9  ldloc.s  4
0x1aabb  ldarg.2
0x1aabc  callvirt instance void class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::RemoveEntry(var<u1>, !!T0)
0x1aac1  ldarg.0
0x1aac2  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheByUName
0x1aac7  ldarg.2
0x1aac8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1aacd  stloc.3
0x1aace  ldloca.s 3
0x1aad0  constrained. [mscorlib]System.Guid
0x1aad6  callvirt instance string [mscorlib]System.Object::ToString()
0x1aadb  ldstr    asc_C09D0// "_"
0x1aae0  ldloc.s  5
0x1aae2  callvirt instance string Microsoft.Crm.Metadata.AppModuleMetadata::get_UniqueName()
0x1aae7  call     string [mscorlib]System.String::Concat(string, string, string)
0x1aaec  ldarg.2
0x1aaed  callvirt instance void class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::RemoveEntry(var<u1>, !!T0)
0x1aaf2  ldarg.2
0x1aaf3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1aaf8  ldc.i4.s 0x47
0x1aafa  ldstr    aAppmodulecache_2// "AppModuleCache.RemoveEntry(): Removed ["...
0x1aaff  ldc.i4.2
0x1ab00  newarr   [mscorlib]System.Object
0x1ab05  dup
0x1ab06  ldc.i4.0
0x1ab07  ldloc.s  5
0x1ab09  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AppModuleMetadata::get_AppModuleId()
0x1ab0e  box      [mscorlib]System.Guid
0x1ab13  stelem.ref
0x1ab14  dup
0x1ab15  ldc.i4.1
0x1ab16  ldloc.s  5
0x1ab18  callvirt instance string Microsoft.Crm.Metadata.AppModuleMetadata::get_Url()
0x1ab1d  stelem.ref
0x1ab1e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ab23  ldarg.2
0x1ab24  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1ab29  ldc.i4.s 0x14
0x1ab2b  ldstr    aRemovedAppmodu// "Removed AppModule {0} from AppModuleCac"...
0x1ab30  ldc.i4.1
0x1ab31  newarr   [mscorlib]System.Object
0x1ab36  dup
0x1ab37  ldc.i4.0
0x1ab38  ldloc.s  5
0x1ab3a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AppModuleMetadata::get_AppModuleId()
0x1ab3f  stloc.3
0x1ab40  ldloca.s 3
0x1ab42  constrained. [mscorlib]System.Guid
0x1ab48  callvirt instance string [mscorlib]System.Object::ToString()
0x1ab4d  stelem.ref
0x1ab4e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ab53  ret
0x1ab54  ldarg.0
0x1ab55  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheByUName
0x1ab5a  ldarg.2
0x1ab5b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1ab60  stloc.3
0x1ab61  ldloca.s 3
0x1ab63  constrained. [mscorlib]System.Guid
0x1ab69  callvirt instance string [mscorlib]System.Object::ToString()
0x1ab6e  ldstr    asc_C09D0// "_"
0x1ab73  ldarg.1
0x1ab74  call     string [mscorlib]System.String::Concat(string, string, string)
0x1ab79  ldarg.2
0x1ab7a  callvirt instance bool class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::ContainsKey(var<u1>, !!T0)
0x1ab7f  brfalse  loc_1AC76
0x1ab84  ldarg.2
0x1ab85  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1ab8a  stloc.3
0x1ab8b  ldloca.s 3
0x1ab8d  constrained. [mscorlib]System.Guid
0x1ab93  callvirt instance string [mscorlib]System.Object::ToString()
0x1ab98  ldstr    asc_C09D0// "_"
0x1ab9d  ldarg.1
0x1ab9e  call     string [mscorlib]System.String::Concat(string, string, string)
0x1aba3  stloc.s  6
0x1aba5  ldarg.0
0x1aba6  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheByUName
0x1abab  ldloc.s  6
0x1abad  ldarg.2
0x1abae  callvirt instance var<u1> class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::LookupEntry(void, var<u1>)
0x1abb3  stloc.s  7
0x1abb5  ldarg.0
0x1abb6  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheById
0x1abbb  ldloc.s  7
0x1abbd  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AppModuleMetadata::get_AppModuleId()
0x1abc2  stloc.3
0x1abc3  ldloca.s 3
0x1abc5  constrained. [mscorlib]System.Guid
0x1abcb  callvirt instance string [mscorlib]System.Object::ToString()
0x1abd0  ldarg.2
0x1abd1  callvirt instance void class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::RemoveEntry(var<u1>, !!T0)
0x1abd6  ldarg.0
0x1abd7  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheByUrl
0x1abdc  ldarg.2
0x1abdd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1abe2  stloc.3
0x1abe3  ldloca.s 3
0x1abe5  constrained. [mscorlib]System.Guid
0x1abeb  callvirt instance string [mscorlib]System.Object::ToString()
0x1abf0  ldstr    asc_C09D0// "_"
0x1abf5  ldloc.s  7
0x1abf7  callvirt instance string Microsoft.Crm.Metadata.AppModuleMetadata::get_UniqueName()
0x1abfc  call     string [mscorlib]System.String::Concat(string, string, string)
0x1ac01  ldarg.2
0x1ac02  callvirt instance void class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::RemoveEntry(var<u1>, !!T0)
0x1ac07  ldarg.0
0x1ac08  ldfld    class Microsoft.Crm.Metadata.AppModuleMetaDataCache Microsoft.Crm.Metadata.AppModuleCache::cacheByUName
0x1ac0d  ldloc.s  6
0x1ac0f  ldarg.2
0x1ac10  callvirt instance void class Microsoft.Crm.Caching.BasicCrmCache`2<string, class Microsoft.Crm.Metadata.AppModuleMetadata>::RemoveEntry(var<u1>, !!T0)
0x1ac15  ldarg.2
0x1ac16  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1ac1b  ldc.i4.s 0x47
0x1ac1d  ldstr    aAppmodulecache_2// "AppModuleCache.RemoveEntry(): Removed ["...
0x1ac22  ldc.i4.2
0x1ac23  newarr   [mscorlib]System.Object
0x1ac28  dup
0x1ac29  ldc.i4.0
0x1ac2a  ldloc.s  7
0x1ac2c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AppModuleMetadata::get_AppModuleId()
0x1ac31  box      [mscorlib]System.Guid
0x1ac36  stelem.ref
0x1ac37  dup
0x1ac38  ldc.i4.1
0x1ac39  ldloc.s  7
0x1ac3b  callvirt instance string Microsoft.Crm.Metadata.AppModuleMetadata::get_Url()
0x1ac40  stelem.ref
0x1ac41  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ac46  ldarg.2
0x1ac47  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1ac4c  ldc.i4.s 0x14
0x1ac4e  ldstr    aRemovedAppmodu// "Removed AppModule {0} from AppModuleCac"...
0x1ac53  ldc.i4.1
0x1ac54  newarr   [mscorlib]System.Object
0x1ac59  dup
0x1ac5a  ldc.i4.0
0x1ac5b  ldloc.s  7
0x1ac5d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.AppModuleMetadata::get_AppModuleId()
0x1ac62  stloc.3
0x1ac63  ldloca.s 3
0x1ac65  constrained. [mscorlib]System.Guid
0x1ac6b  callvirt instance string [mscorlib]System.Object::ToString()
0x1ac70  stelem.ref
0x1ac71  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ac76  ret
```
