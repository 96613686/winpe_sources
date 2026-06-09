# Microsoft.Crm.Caching.ActionCardUserSettingsCacheData::Initialize

- ea: `0x80cc0`
- end: `0x80e92`
- name: `Microsoft.Crm.Caching.ActionCardUserSettingsCacheData::Initialize`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x80c80`
- `0x80c90`
- `0x80cc0`
- `0x80ea0`
- `0x86390`
- `0x96cd0`
- `0x9bd00`
- `0x9bd20`
- `0x9c490`
- `0x9c500`
- `0x9d270`
- `0xa88f0`

## string_xrefs

- `0x80e14`: `ActionCardUserSettingsCache`
- `0x80e77`: `ActionCardUserSettingsCache`

## pseudocode

```c

```

## disassembly

```asm
0x80cc0  ldarg.0
0x80cc1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x80cc6  stfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.Crm.Caching.ActionCardUserSettingsCacheData::_enabledCRMCardTypes
0x80ccb  ldarg.0
0x80ccc  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Caching.IActionCardOption>::.ctor()
0x80cd1  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Caching.IActionCardOption> Microsoft.Crm.Caching.ActionCardUserSettingsCacheData::_cardOptions
0x80cd6  ldarg.0
0x80cd7  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x80cdc  stfld    class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.Crm.Caching.ActionCardUserSettingsCacheData::_enabledExchangeCardTypes
0x80ce1  call     class Microsoft.Crm.Caching.OrganizationCache Microsoft.Crm.Caching.OrganizationCache::Instance()
0x80ce6  ldarg.2
0x80ce7  ldarg.2
0x80ce8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x80ced  callvirt instance var<u1> class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x80cf2  callvirt instance bool Microsoft.Crm.Caching.IOrganizationSettings::get_IsActionCardEnabled()
0x80cf7  stloc.0
0x80cf8  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x80cfd  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x80d02  ldc.i4.2
0x80d03  bne.un.s loc_80D0D
0x80d05  ldarg.0
0x80d06  ldfld    bool Microsoft.Crm.Caching.ActionCardUserSettingsCacheData::_isSSSConfiguredForUser
0x80d0b  br.s     loc_80D0E
0x80d0d  ldc.i4.0
0x80d0e  stloc.1
0x80d0f  ldc.i4.0
0x80d10  stloc.2
0x80d11  br       loc_80E85
0x80d16  ldarg.1
0x80d17  ldloc.2
0x80d18  callvirt instance class Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32 index)
0x80d1d  stloc.3
0x80d1e  ldc.i4.0
0x80d1f  stloc.s  4
0x80d21  ldloc.3
0x80d22  callvirt instance class Microsoft.Crm.BusinessEntities.IAttributeInfoCollection Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x80d27  ldstr    aActioncarduser// "actionCardUserSettings.isenabled"
0x80d2c  callvirt instance bool Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::Contains(string attributeName)
0x80d31  brfalse.s loc_80D52
0x80d33  ldloc.3
0x80d34  callvirt instance class Microsoft.Crm.BusinessEntities.IAttributeInfoCollection Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x80d39  ldstr    aActioncarduser// "actionCardUserSettings.isenabled"
0x80d3e  callvirt instance class Microsoft.Crm.BusinessEntities.IAttributeInfo Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string name)
0x80d43  callvirt instance object Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x80d48  unbox.any [mscorlib]System.Boolean
0x80d4d  brfalse  loc_80E81
0x80d52  ldloc.3
0x80d53  ldstr    aIsliveonly// "isliveonly"
0x80d58  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x80d5d  unbox.any [mscorlib]System.Boolean
0x80d62  brtrue.s loc_80D9F
0x80d64  ldloc.3
0x80d65  ldstr    aIsbasecard// "isbasecard"
0x80d6a  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x80d6f  unbox.any [mscorlib]System.Boolean
0x80d74  ldloc.0
0x80d75  or
0x80d76  brfalse.s loc_80DEC
0x80d78  ldarg.0
0x80d79  call     instance class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.Crm.Caching.ActionCardUserSettingsCacheData::get_EnabledCRMCardTypes()
0x80d7e  ldloc.3
0x80d7f  ldstr    aCardtype// "cardtype"
0x80d84  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x80d89  unbox.any [mscorlib]System.Int32
0x80d8e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x80d93  ldarg.0
0x80d94  ldloc.3
0x80d95  call     instance void Microsoft.Crm.Caching.ActionCardUserSettingsCacheData::AddEnabledCard(class Microsoft.Crm.BusinessEntities.BusinessEntity record)
0x80d9a  ldc.i4.1
0x80d9b  stloc.s  4
0x80d9d  br.s     loc_80DEC
0x80d9f  ldloc.3
0x80da0  ldstr    aIsliveonly// "isliveonly"
0x80da5  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x80daa  unbox.any [mscorlib]System.Boolean
0x80daf  ldloc.1
0x80db0  and
0x80db1  brfalse.s loc_80DEC
0x80db3  ldloc.3
0x80db4  ldstr    aIsbasecard// "isbasecard"
0x80db9  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x80dbe  unbox.any [mscorlib]System.Boolean
0x80dc3  ldloc.0
0x80dc4  or
0x80dc5  brfalse.s loc_80DEC
0x80dc7  ldarg.0
0x80dc8  call     instance class [mscorlib]System.Collections.Generic.List`1<int32> Microsoft.Crm.Caching.ActionCardUserSettingsCacheData::get_EnabledExchangeCardTypes()
0x80dcd  ldloc.3
0x80dce  ldstr    aCardtype// "cardtype"
0x80dd3  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x80dd8  unbox.any [mscorlib]System.Int32
0x80ddd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x80de2  ldarg.0
0x80de3  ldloc.3
0x80de4  call     instance void Microsoft.Crm.Caching.ActionCardUserSettingsCacheData::AddEnabledCard(class Microsoft.Crm.BusinessEntities.BusinessEntity record)
0x80de9  ldc.i4.1
0x80dea  stloc.s  4
0x80dec  ldloc.s  4
0x80dee  brfalse.s loc_80E20
0x80df0  call     class [Microsoft.Crm]Microsoft.Crm.CacheEventSource [Microsoft.Crm]Microsoft.Crm.CacheEventSource::get_Instance()
0x80df5  ldstr    aCardType0// "Card type: {0}"
0x80dfa  ldloc.3
0x80dfb  ldstr    aCardtype// "cardtype"
0x80e00  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x80e05  unbox.any [mscorlib]System.Int32
0x80e0a  box      [mscorlib]System.Int32
0x80e0f  call     string [mscorlib]System.String::Format(string, object)
0x80e14  ldstr    aActioncarduser_0// "ActionCardUserSettingsCache"
0x80e19  callvirt instance void [Microsoft.Crm]Microsoft.Crm.CacheEventSource::AddCacheEntryEnded(string, string)
0x80e1e  br.s     loc_80E81
0x80e20  call     class [Microsoft.Crm]Microsoft.Crm.CacheEventSource [Microsoft.Crm]Microsoft.Crm.CacheEventSource::get_Instance()
0x80e25  ldstr    aCardType0Isliv// "Card type: {0}, isliveonly: {1}, isRIPr"...
0x80e2a  ldc.i4.4
0x80e2b  newarr   [mscorlib]System.Object
0x80e30  dup
0x80e31  ldc.i4.0
0x80e32  ldloc.3
0x80e33  ldstr    aCardtype// "cardtype"
0x80e38  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x80e3d  unbox.any [mscorlib]System.Int32
0x80e42  box      [mscorlib]System.Int32
0x80e47  stelem.ref
0x80e48  dup
0x80e49  ldc.i4.1
0x80e4a  ldloc.3
0x80e4b  ldstr    aIsliveonly// "isliveonly"
0x80e50  callvirt instance object Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string attributeName)
0x80e55  unbox.any [mscorlib]System.Boolean
0x80e5a  box      [mscorlib]System.Boolean
0x80e5f  stelem.ref
0x80e60  dup
0x80e61  ldc.i4.2
0x80e62  ldloc.0
0x80e63  box      [mscorlib]System.Boolean
0x80e68  stelem.ref
0x80e69  dup
0x80e6a  ldc.i4.3
0x80e6b  ldloc.1
0x80e6c  box      [mscorlib]System.Boolean
0x80e71  stelem.ref
0x80e72  call     string [mscorlib]System.String::Format(string, object[])
0x80e77  ldstr    aActioncarduser_0// "ActionCardUserSettingsCache"
0x80e7c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.CacheEventSource::CacheEntryMissed(string, string)
0x80e81  ldloc.2
0x80e82  ldc.i4.1
0x80e83  add
0x80e84  stloc.2
0x80e85  ldloc.2
0x80e86  ldarg.1
0x80e87  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x80e8c  blt      loc_80D16
0x80e91  ret
```
