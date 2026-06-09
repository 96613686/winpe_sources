# Microsoft.Crm.ConfigurationDatabase.StaticEncryptionConfigurationCache::LoadEncryptionKeys

- ea: `0x49f10`
- end: `0x4a004`
- name: `Microsoft.Crm.ConfigurationDatabase.StaticEncryptionConfigurationCache::LoadEncryptionKeys`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x49e60`

## callees

- `0x2d930`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x49f10`
- `0x4d750`
- `0x5f760`
- `0x5f780`
- `0x61520`

## string_xrefs

- `0x49f23`: `IsConfigurationRow`
- `0x49f6b`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\Cache\EncryptionConfigurationCache.cs`

## pseudocode

```c

```

## disassembly

```asm
0x49f10  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.SharedDatabase.CrmEncryptionKey, class Microsoft.Crm.SharedDatabase.EncryptionKeyInfo>::.ctor()
0x49f15  stloc.0
0x49f16  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x49f1b  stloc.1
0x49f1c  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x49f21  stloc.2
0x49f22  ldloc.2
0x49f23  ldstr    aIsconfiguratio// "IsConfigurationRow"
0x49f28  ldc.i4.0
0x49f29  box      [mscorlib]System.Boolean
0x49f2e  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x49f33  ldloc.1
0x49f34  ldstr    aDataencryption// "DataEncryptionKey"
0x49f39  ldc.i4.3
0x49f3a  newarr   [mscorlib]System.String
0x49f3f  dup
0x49f40  ldc.i4.0
0x49f41  ldstr    aCrmkeyname// "CrmKeyName"
0x49f46  stelem.ref
0x49f47  dup
0x49f48  ldc.i4.1
0x49f49  ldstr    aPhysicalkeynam// "PhysicalKeyName"
0x49f4e  stelem.ref
0x49f4f  dup
0x49f50  ldc.i4.2
0x49f51  ldstr    aId// "Id"
0x49f56  stelem.ref
0x49f57  ldc.i4.1
0x49f58  newarr   Microsoft.Crm.Data.PropertyBag
0x49f5d  dup
0x49f5e  ldc.i4.0
0x49f5f  ldloc.2
0x49f60  stelem.ref
0x49f61  ldc.i4   0xA1
0x49f66  ldstr    aLoadencryption_0// "LoadEncryptionKeys"
0x49f6b  ldstr    aDA1SSrcPlatfor_32// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x49f70  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x49f75  stloc.3
0x49f76  ldloc.3
0x49f77  brfalse.s loc_49FF6
0x49f79  ldloc.3
0x49f7a  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x49f7f  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x49f84  stloc.s  4
0x49f86  br.s     loc_49FDD
0x49f88  ldloca.s 4
0x49f8a  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x49f8f  stloc.s  5
0x49f91  ldtoken  Microsoft.Crm.SharedDatabase.CrmEncryptionKey
0x49f96  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x49f9b  ldloc.s  5
0x49f9d  ldstr    aCrmkeyname// "CrmKeyName"
0x49fa2  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x49fa7  castclass [mscorlib]System.String
0x49fac  call     object Microsoft.Crm.CrmEnumUtility::ParseSingleValue(class [mscorlib]System.Type enumType, string value)
0x49fb1  unbox.any Microsoft.Crm.SharedDatabase.CrmEncryptionKey
0x49fb6  ldloc.s  5
0x49fb8  ldstr    aPhysicalkeynam// "PhysicalKeyName"
0x49fbd  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x49fc2  castclass [mscorlib]System.String
0x49fc7  newobj   instance void Microsoft.Crm.SharedDatabase.EncryptionKeyInfo::.ctor(valuetype Microsoft.Crm.SharedDatabase.CrmEncryptionKey crmEncryptionKey, string symmetricKeyName)
0x49fcc  stloc.s  6
0x49fce  ldloc.0
0x49fcf  ldloc.s  6
0x49fd1  callvirt instance valuetype Microsoft.Crm.SharedDatabase.CrmEncryptionKey Microsoft.Crm.SharedDatabase.EncryptionKeyInfo::get_CrmEncryptionKey()
0x49fd6  ldloc.s  6
0x49fd8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.SharedDatabase.CrmEncryptionKey, class Microsoft.Crm.SharedDatabase.EncryptionKeyInfo>::Add(var<u1>, !!T0)
0x49fdd  ldloca.s 4
0x49fdf  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x49fe4  brtrue.s loc_49F88
0x49fe6  leave.s  loc_4A002
0x49fe8  ldloca.s 4
0x49fea  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x49ff0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49ff5  endfinally
0x49ff6  leave.s  loc_4A002
0x49ff8  ldloc.1
0x49ff9  brfalse.s loc_4A001
0x49ffb  ldloc.1
0x49ffc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a001  endfinally
0x4a002  ldloc.0
0x4a003  ret
```
