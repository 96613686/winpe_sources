# Microsoft.Crm.LocatorCache::NotificationHandler

- ea: `0x3760`
- end: `0x3b79`
- name: `Microsoft.Crm.LocatorCache::NotificationHandler`
- size: `1049`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1f80`
- `0x3440`
- `0x3510`
- `0x35f0`
- `0x3610`
- `0x3760`
- `0x3b80`
- `0x3ba0`
- `0x4030`
- `0x4120`
- `0x13a50`
- `0x13a60`
- `0x13a70`
- `0x17d80`
- `0x1e960`
- `0x1eaa0`
- `0x1f4f0`
- `0x5db20`
- `0x5dd70`

## string_xrefs

- `0x3944`: `@Live.com`
- `0x395f`: `@MicrosoftOnline.com`
- `0x3b30`: `LocatorCache received unexpected Notification event data`
- `0x3b5e`: `LocatorCache received unexpected Notification event data`

## pseudocode

```c

```

## disassembly

```asm
0x3760  ldarg.1
0x3761  callvirt instance valuetype Microsoft.Crm.LocatorServiceContext Microsoft.Crm.NotificationEventArgs::get_LocatorServiceContext()
0x3766  ldarg.0
0x3767  ldfld    valuetype Microsoft.Crm.LocatorServiceContext Microsoft.Crm.LocatorCache::_locatorServiceContext
0x376c  beq.s    loc_376F
0x376e  ret
0x376f  call     void Microsoft.Crm.CrmTrace::LocatorServiceUpdated()
0x3774  ldc.i4.s 0x19
0x3776  ldarg.1
0x3777  callvirt instance valuetype Microsoft.Crm.NotificationEventType Microsoft.Crm.NotificationEventArgs::get_EventId()
0x377c  bne.un.s loc_378B
0x377e  ldarg.0
0x377f  call     instance void Microsoft.Crm.LocatorCache::RemoveAll()
0x3784  ldarg.0
0x3785  call     instance void Microsoft.Crm.LocatorCache::UpdateTotalFlushCount()
0x378a  ret
0x378b  ldc.i4.s 0x1D
0x378d  ldarg.1
0x378e  callvirt instance valuetype Microsoft.Crm.NotificationEventType Microsoft.Crm.NotificationEventArgs::get_EventId()
0x3793  beq.s    loc_37B6
0x3795  ldc.i4.s 0x1E
0x3797  ldarg.1
0x3798  callvirt instance valuetype Microsoft.Crm.NotificationEventType Microsoft.Crm.NotificationEventArgs::get_EventId()
0x379d  beq.s    loc_37B6
0x379f  ldc.i4.s 0x1F
0x37a1  ldarg.1
0x37a2  callvirt instance valuetype Microsoft.Crm.NotificationEventType Microsoft.Crm.NotificationEventArgs::get_EventId()
0x37a7  beq.s    loc_37B6
0x37a9  ldc.i4.s 0x20
0x37ab  ldarg.1
0x37ac  callvirt instance valuetype Microsoft.Crm.NotificationEventType Microsoft.Crm.NotificationEventArgs::get_EventId()
0x37b1  bne.un   loc_389A
0x37b6  ldarg.0
0x37b7  ldc.i4.3
0x37b8  ldc.i4.0
0x37b9  newarr   [mscorlib]System.Object
0x37be  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object[] keys)
0x37c3  ldarg.0
0x37c4  ldc.i4.s 0xB
0x37c6  ldc.i4.0
0x37c7  newarr   [mscorlib]System.Object
0x37cc  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object[] keys)
0x37d1  ldarg.0
0x37d2  ldc.i4.4
0x37d3  ldc.i4.0
0x37d4  newarr   [mscorlib]System.Object
0x37d9  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object[] keys)
0x37de  ldarg.0
0x37df  ldfld    class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor Microsoft.Crm.LocatorCache::_locatorCacheSettingAccessor
0x37e4  callvirt instance class Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettings Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.ILocatorCacheSettingAccessor::get_Settings()
0x37e9  callvirt instance bool Microsoft.Crm.Core.DataServices.Configuration.LocatorService.LocatorCache.LocatorCacheSettings::get_IsRetrieveConditionCacheEnabled()
0x37ee  brtrue.s loc_3818
0x37f0  ldarg.0
0x37f1  ldc.i4.6
0x37f2  ldc.i4.0
0x37f3  newarr   [mscorlib]System.Object
0x37f8  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object[] keys)
0x37fd  ldarg.0
0x37fe  ldc.i4.7
0x37ff  ldc.i4.0
0x3800  newarr   [mscorlib]System.Object
0x3805  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object[] keys)
0x380a  ldarg.0
0x380b  ldc.i4.s 0xD
0x380d  ldc.i4.0
0x380e  newarr   [mscorlib]System.Object
0x3813  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object[] keys)
0x3818  ldloca.s 1
0x381a  ldarg.1
0x381b  callvirt instance string Microsoft.Crm.NotificationEventArgs::get_EventData()
0x3820  call     instance void [mscorlib]System.Guid::.ctor(string)
0x3825  ldarg.0
0x3826  ldstr    aOrganization// "Organization"
0x382b  ldloc.1
0x382c  box      [mscorlib]System.Guid
0x3831  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(string tableName, object primaryKey)
0x3836  ldsfld   string[] Microsoft.Crm.SharedDatabase.DatabaseService::OrganizationEncryptedColumns
0x383b  stloc.2
0x383c  ldc.i4.0
0x383d  stloc.3
0x383e  br.s     loc_3866
0x3840  ldloc.2
0x3841  ldloc.3
0x3842  ldelem.ref
0x3843  stloc.s  4
0x3845  ldarg.0
0x3846  ldstr    aOrganization// "Organization"
0x384b  ldloc.1
0x384c  box      [mscorlib]System.Guid
0x3851  ldstr    asc_70C26// "_"
0x3856  ldloc.s  4
0x3858  call     string [mscorlib]System.String::Concat(object, object, object)
0x385d  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(string tableName, object primaryKey)
0x3862  ldloc.3
0x3863  ldc.i4.1
0x3864  add
0x3865  stloc.3
0x3866  ldloc.3
0x3867  ldloc.2
0x3868  ldlen
0x3869  conv.i4
0x386a  blt.s    loc_3840
0x386c  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.BootstrapService::GetSku()
0x3871  ldc.i4.2
0x3872  bne.un.s loc_3893
0x3874  ldstr    aOrganizationli// "OrganizationLifecycle"
0x3879  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x387e  ldloc.1
0x387f  box      [mscorlib]System.Guid
0x3884  call     string Microsoft.Crm.LocatorCacheKey::CreateCacheKey(string tableName, string columnName, object columnValue)
0x3889  stloc.s  5
0x388b  ldarg.0
0x388c  ldloc.s  5
0x388e  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(string cacheKey)
0x3893  ldarg.0
0x3894  call     instance void Microsoft.Crm.LocatorCache::UpdateTotalFlushCount()
0x3899  ret
0x389a  ldc.i4.2
0x389b  ldarg.1
0x389c  callvirt instance valuetype Microsoft.Crm.NotificationEventType Microsoft.Crm.NotificationEventArgs::get_EventId()
0x38a1  bne.un.s loc_38FA
0x38a3  ldloca.s 6
0x38a5  ldarg.1
0x38a6  callvirt instance string Microsoft.Crm.NotificationEventArgs::get_EventData()
0x38ab  call     instance void [mscorlib]System.Guid::.ctor(string)
0x38b0  ldarg.0
0x38b1  ldstr    aOrganization// "Organization"
0x38b6  ldloc.s  6
0x38b8  box      [mscorlib]System.Guid
0x38bd  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(string tableName, object primaryKey)
0x38c2  ldsfld   string[] Microsoft.Crm.SharedDatabase.DatabaseService::OrganizationEncryptedColumns
0x38c7  stloc.2
0x38c8  ldc.i4.0
0x38c9  stloc.3
0x38ca  br.s     loc_38F3
0x38cc  ldloc.2
0x38cd  ldloc.3
0x38ce  ldelem.ref
0x38cf  stloc.s  7
0x38d1  ldarg.0
0x38d2  ldstr    aOrganization// "Organization"
0x38d7  ldloc.s  6
0x38d9  box      [mscorlib]System.Guid
0x38de  ldstr    asc_70C26// "_"
0x38e3  ldloc.s  7
0x38e5  call     string [mscorlib]System.String::Concat(object, object, object)
0x38ea  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(string tableName, object primaryKey)
0x38ef  ldloc.3
0x38f0  ldc.i4.1
0x38f1  add
0x38f2  stloc.3
0x38f3  ldloc.3
0x38f4  ldloc.2
0x38f5  ldlen
0x38f6  conv.i4
0x38f7  blt.s    loc_38CC
0x38f9  ret
0x38fa  ldarg.1
0x38fb  callvirt instance valuetype Microsoft.Crm.NotificationEventType Microsoft.Crm.NotificationEventArgs::get_EventId()
0x3900  brtrue.s loc_3903
0x3902  ret
0x3903  ldc.i4.s 0x26
0x3905  ldarg.1
0x3906  callvirt instance valuetype Microsoft.Crm.NotificationEventType Microsoft.Crm.NotificationEventArgs::get_EventId()
0x390b  bne.un   loc_39B1
0x3910  ldarg.1
0x3911  callvirt instance string Microsoft.Crm.NotificationEventArgs::get_EventData()
0x3916  ldstr    aCrmuserorganiz// "CrmUserOrganizations:P:"
0x391b  ldc.i4.5
0x391c  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x3921  brfalse.s loc_3973
0x3923  ldarg.1
0x3924  callvirt instance string Microsoft.Crm.NotificationEventArgs::get_EventData()
0x3929  ldc.i4.1
0x392a  newarr   [mscorlib]System.Char
0x392f  dup
0x3930  ldc.i4.0
0x3931  ldc.i4.s 0x3A
0x3933  stelem.i2
0x3934  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x3939  ldc.i4.2
0x393a  ldelem.ref
0x393b  stloc.s  8
0x393d  ldstr    aCrmuserorganiz_0// "CrmUserOrganizations:C:"
0x3942  ldloc.s  8
0x3944  ldstr    aLiveCom// "@Live.com"
0x3949  call     string [mscorlib]System.String::Concat(string, string, string)
0x394e  stloc.s  9
0x3950  ldarg.0
0x3951  ldloc.s  9
0x3953  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(string cacheKey)
0x3958  ldstr    aCrmuserorganiz_0// "CrmUserOrganizations:C:"
0x395d  ldloc.s  8
0x395f  ldstr    aMicrosoftonlin// "@MicrosoftOnline.com"
0x3964  call     string [mscorlib]System.String::Concat(string, string, string)
0x3969  stloc.s  0xA
0x396b  ldarg.0
0x396c  ldloc.s  0xA
0x396e  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(string cacheKey)
0x3973  ldarg.0
0x3974  ldarg.1
0x3975  callvirt instance string Microsoft.Crm.NotificationEventArgs::get_EventData()
0x397a  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(string cacheKey)
0x397f  ldsfld   string[] Microsoft.Crm.SharedDatabase.DatabaseService::OrganizationEncryptedColumns
0x3984  stloc.2
0x3985  ldc.i4.0
0x3986  stloc.3
0x3987  br.s     loc_39AA
0x3989  ldloc.2
0x398a  ldloc.3
0x398b  ldelem.ref
0x398c  stloc.s  0xB
0x398e  ldarg.0
0x398f  ldarg.1
0x3990  callvirt instance string Microsoft.Crm.NotificationEventArgs::get_EventData()
0x3995  ldstr    asc_70C26// "_"
0x399a  ldloc.s  0xB
0x399c  call     string [mscorlib]System.String::Concat(string, string, string)
0x39a1  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(string cacheKey)
0x39a6  ldloc.3
0x39a7  ldc.i4.1
0x39a8  add
0x39a9  stloc.3
0x39aa  ldloc.3
0x39ab  ldloc.2
0x39ac  ldlen
0x39ad  conv.i4
0x39ae  blt.s    loc_3989
0x39b0  ret
0x39b1  ldc.i4.s 0x1A
0x39b3  ldarg.1
0x39b4  callvirt instance valuetype Microsoft.Crm.NotificationEventType Microsoft.Crm.NotificationEventArgs::get_EventId()
0x39b9  bne.un.s loc_39F3
0x39bb  ldloca.s 0xC
0x39bd  ldarg.1
0x39be  callvirt instance string Microsoft.Crm.NotificationEventArgs::get_EventData()
0x39c3  call     instance void [mscorlib]System.Guid::.ctor(string)
0x39c8  ldarg.0
0x39c9  ldstr    aScalegroup// "ScaleGroup"
0x39ce  ldloc.s  0xC
0x39d0  box      [mscorlib]System.Guid
0x39d5  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(string tableName, object primaryKey)
0x39da  ldarg.0
0x39db  ldc.i4.s 0x15
0x39dd  ldc.i4.1
0x39de  newarr   [mscorlib]System.Object
0x39e3  dup
0x39e4  ldc.i4.0
0x39e5  ldloc.s  0xC
0x39e7  box      [mscorlib]System.Guid
0x39ec  stelem.ref
0x39ed  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object[] keys)
0x39f2  ret
0x39f3  ldc.i4   0x84
0x39f8  ldarg.1
0x39f9  callvirt instance valuetype Microsoft.Crm.NotificationEventType Microsoft.Crm.NotificationEventArgs::get_EventId()
0x39fe  bne.un.s loc_3A26
0x3a00  ldloca.s 0xD
0x3a02  ldarg.1
0x3a03  callvirt instance string Microsoft.Crm.NotificationEventArgs::get_EventData()
0x3a08  call     instance void [mscorlib]System.Guid::.ctor(string)
0x3a0d  ldarg.0
0x3a0e  ldc.i4.s 0x15
0x3a10  ldc.i4.1
0x3a11  newarr   [mscorlib]System.Object
0x3a16  dup
0x3a17  ldc.i4.0
0x3a18  ldloc.s  0xD
0x3a1a  box      [mscorlib]System.Guid
0x3a1f  stelem.ref
0x3a20  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object[] keys)
0x3a25  ret
0x3a26  ldc.i4.s 0x43
0x3a28  ldarg.1
0x3a29  callvirt instance valuetype Microsoft.Crm.NotificationEventType Microsoft.Crm.NotificationEventArgs::get_EventId()
0x3a2e  bne.un.s loc_3A51
0x3a30  ldarg.1
0x3a31  callvirt instance string Microsoft.Crm.NotificationEventArgs::get_EventData()
0x3a36  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x3a3b  stloc.s  0xE
0x3a3d  ldarg.0
0x3a3e  ldc.i4.s 0x10
0x3a40  ldc.i4.1
0x3a41  newarr   [mscorlib]System.Object
0x3a46  dup
0x3a47  ldc.i4.0
0x3a48  ldloc.s  0xE
0x3a4a  stelem.ref
0x3a4b  call     instance void Microsoft.Crm.LocatorCache::RemoveEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object[] keys)
0x3a50  ret
0x3a51  ldc.i4.s 0x29
0x3a53  ldarg.1
0x3a54  callvirt instance valuetype Microsoft.Crm.NotificationEventType Microsoft.Crm.NotificationEventArgs::get_EventId()
0x3a59  bne.un.s loc_3A77
0x3a5b  ldarg.1
0x3a5c  callvirt instance string Microsoft.Crm.NotificationEventArgs::get_EventData()
0x3a61  stloc.s  0xF
0x3a63  ldarg.0
0x3a64  ldc.i4.s 0xF
0x3a66  ldc.i4.1
  ... truncated ...
```
