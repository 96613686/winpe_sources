# Microsoft.Crm.CrmCache`1::RegisterEvents

- ea: `0x1bdb0`
- end: `0x1be8a`
- name: `Microsoft.Crm.CrmCache`1::RegisterEvents`
- size: `218`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1bdb0`

## string_xrefs

- `0x1bdc8`: `OverrideLabelDictionaryCache`
- `0x1be57`: `OverrideLabelDictionaryCache`
- `0x1bde4`: ` should not register for the netCacheItemRemove event - only the CrmCache and OverrideLabelDictionaryCache should register for that`
- `0x1be03`: ` should not register for the netHardExpiry event - only the CrmCache should register for that`

## pseudocode

```c

```

## disassembly

```asm
0x1bdb0  ldarg.1
0x1bdb1  brfalse.s loc_1BE25
0x1bdb3  ldarg.2
0x1bdb4  ldstr    aNotificationha// "notificationHandler"
0x1bdb9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1bdbe  ldc.i4.0
0x1bdbf  stloc.0
0x1bdc0  br.s     loc_1BE1F
0x1bdc2  ldarg.0
0x1bdc3  ldfld    string class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheIdentifier
0x1bdc8  ldstr    aOverridelabeld// "OverrideLabelDictionaryCache"
0x1bdcd  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1bdd2  brfalse.s loc_1BDF3
0x1bdd4  ldarg.1
0x1bdd5  ldloc.0
0x1bdd6  ldelem.i4
0x1bdd7  ldc.i4.s 0x23
0x1bdd9  ceq
0x1bddb  ldc.i4.0
0x1bddc  ceq
0x1bdde  ldarg.0
0x1bddf  ldfld    string class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheIdentifier
0x1bde4  ldstr    aShouldNotRegis// " should not register for the netCacheIt"...
0x1bde9  call     string [mscorlib]System.String::Concat(string, string)
0x1bdee  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1bdf3  ldarg.1
0x1bdf4  ldloc.0
0x1bdf5  ldelem.i4
0x1bdf6  ldc.i4.s 0xE
0x1bdf8  ceq
0x1bdfa  ldc.i4.0
0x1bdfb  ceq
0x1bdfd  ldarg.0
0x1bdfe  ldfld    string class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheIdentifier
0x1be03  ldstr    aShouldNotRegis_0// " should not register for the netHardExp"...
0x1be08  call     string [mscorlib]System.String::Concat(string, string)
0x1be0d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1be12  ldarg.1
0x1be13  ldloc.0
0x1be14  ldelem.i4
0x1be15  ldarg.2
0x1be16  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0x1be1b  ldloc.0
0x1be1c  ldc.i4.1
0x1be1d  add
0x1be1e  stloc.0
0x1be1f  ldloc.0
0x1be20  ldarg.1
0x1be21  ldlen
0x1be22  conv.i4
0x1be23  blt.s    loc_1BDC2
0x1be25  ldarg.0
0x1be26  ldarg.0
0x1be27  ldftn    instance void class Microsoft.Crm.CrmCache`1<var<u1>>::ItemRemoved(string, object, valuetype [System.Web]System.Web.Caching.CacheItemRemovedReason)
0x1be2d  newobj   instance void [System.Web]System.Web.Caching.CacheItemRemovedCallback::.ctor(object, native int)
0x1be32  stfld    class [System.Web]System.Web.Caching.CacheItemRemovedCallback class Microsoft.Crm.CrmCache`1<var<u1>>::_itemRemovedCallback
0x1be37  ldarg.0
0x1be38  call     instance bool class Microsoft.Crm.CrmCache`1<var<u1>>::get_EnableMemoryCache()
0x1be3d  brfalse.s loc_1BE51
0x1be3f  ldarg.0
0x1be40  ldarg.0
0x1be41  ldftn    instance void class Microsoft.Crm.CrmCache`1<var<u1>>::OnMemoryCacheItemRemovedCallback(class [System.Runtime.Caching]System.Runtime.Caching.CacheEntryRemovedArguments)
0x1be47  newobj   instance void [System.Runtime.Caching]System.Runtime.Caching.CacheEntryRemovedCallback::.ctor(object, native int)
0x1be4c  stfld    class [System.Runtime.Caching]System.Runtime.Caching.CacheEntryRemovedCallback class Microsoft.Crm.CrmCache`1<var<u1>>::_memoryCacheItemRemovedCallback
0x1be51  ldarg.0
0x1be52  ldfld    string class Microsoft.Crm.CrmCache`1<var<u1>>::_cacheIdentifier
0x1be57  ldstr    aOverridelabeld// "OverrideLabelDictionaryCache"
0x1be5c  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1be61  brfalse.s loc_1BE76
0x1be63  ldc.i4.s 0x23
0x1be65  ldarg.0
0x1be66  ldftn    instance void class Microsoft.Crm.CrmCache`1<var<u1>>::CacheItemRemoveHandler(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs)
0x1be6c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0x1be71  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0x1be76  ldc.i4.s 0xE
0x1be78  ldarg.0
0x1be79  ldftn    instance void class Microsoft.Crm.CrmCache`1<var<u1>>::HardExpiryHandler(class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs)
0x1be7f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler::.ctor(object, native int)
0x1be84  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::RegisterEventHandler(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, class [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventHandler)
0x1be89  ret
```
