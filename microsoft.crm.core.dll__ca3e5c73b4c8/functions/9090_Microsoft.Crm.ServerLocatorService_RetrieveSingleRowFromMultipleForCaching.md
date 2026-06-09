# Microsoft.Crm.ServerLocatorService::RetrieveSingleRowFromMultipleForCaching

- ea: `0x9090`
- end: `0x9211`
- name: `Microsoft.Crm.ServerLocatorService::RetrieveSingleRowFromMultipleForCaching`
- size: `385`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x8ff0`

## callees

- `0x30f0`
- `0x3140`
- `0x9090`
- `0xbfa0`
- `0x1a880`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x44600`
- `0x44800`
- `0x44d80`
- `0x44d90`
- `0x4a610`
- `0x4d750`
- `0x5f120`
- `0x5f5d0`
- `0x607f0`
- `0x60800`
- `0x60850`
- `0x61520`

## string_xrefs

- `0x9170`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x9090  ldnull
0x9091  stloc.0
0x9092  call     class Microsoft.Crm.SharedDatabase.DBMetadataCache Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::get_Cache()
0x9097  callvirt instance class Microsoft.Crm.SharedDatabase.TableCollection Microsoft.Crm.SharedDatabase.DBMetadataCache::get_Tables()
0x909c  ldarg.1
0x909d  ldloca.s 0
0x909f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.SharedDatabase.Table>::TryGetValue(var<u1>, !!T0)
0x90a4  brtrue.s loc_90C1
0x90a6  ldstr    aTableWithName// "Table with name '"
0x90ab  ldarg.1
0x90ac  ldstr    aWasNotFound// "' was not found"
0x90b1  call     string [mscorlib]System.String::Concat(string, string, string)
0x90b6  ldc.i4   0x80040216
0x90bb  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message, int32 errorCode)
0x90c0  throw
0x90c1  ldloc.0
0x90c2  callvirt instance bool Microsoft.Crm.SharedDatabase.Table::get_CachedByLocator()
0x90c7  brfalse  loc_920F
0x90cc  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x90d1  stloc.1
0x90d2  ldarg.3
0x90d3  callvirt instance class [mscorlib]System.Collections.IEnumerable Microsoft.Crm.Data.PropertyBag::get_PropertyEntries()
0x90d8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x90dd  stloc.3
0x90de  br.s     loc_9101
0x90e0  ldloc.3
0x90e1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x90e6  unbox.any Microsoft.Crm.Data.PropertyEntry
0x90eb  stloc.s  4
0x90ed  ldloc.1
0x90ee  ldloca.s 4
0x90f0  call     instance string Microsoft.Crm.Data.PropertyEntry::get_Name()
0x90f5  ldloca.s 4
0x90f7  call     instance class Microsoft.Crm.Data.IProperty Microsoft.Crm.Data.PropertyEntry::get_Property()
0x90fc  callvirt instance void Microsoft.Crm.Data.PropertyBag::Add(string propertyName, class Microsoft.Crm.Data.IProperty newProperty)
0x9101  ldloc.3
0x9102  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9107  brtrue.s loc_90E0
0x9109  leave.s  loc_911F
0x910b  ldloc.3
0x910c  isinst   [mscorlib]System.IDisposable
0x9111  stloc.s  5
0x9113  ldloc.s  5
0x9115  brfalse.s loc_911E
0x9117  ldloc.s  5
0x9119  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x911e  endfinally
0x911f  ldloc.1
0x9120  ldarg.s  4
0x9122  ldarg.s  5
0x9124  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x9129  ldarg.0
0x912a  ldfld    class Microsoft.Crm.ILocatorCache Microsoft.Crm.ServerLocatorService::_cache
0x912f  ldloc.0
0x9130  ldloc.1
0x9131  callvirt instance object Microsoft.Crm.ILocatorCache::LookupEntry(class Microsoft.Crm.SharedDatabase.Table table, class Microsoft.Crm.Data.PropertyBag conditions)
0x9136  isinst   Microsoft.Crm.Data.PropertyBag
0x913b  stloc.2
0x913c  ldloc.2
0x913d  brtrue   loc_920A
0x9142  ldnull
0x9143  stloc.s  6
0x9145  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x914a  stloc.s  7
0x914c  ldloc.s  7
0x914e  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0x9153  ldloc.s  7
0x9155  ldloc.0
0x9156  callvirt instance string Microsoft.Crm.SharedDatabase.Table::get_Name()
0x915b  ldarg.2
0x915c  ldc.i4.1
0x915d  newarr   Microsoft.Crm.Data.PropertyBag
0x9162  dup
0x9163  ldc.i4.0
0x9164  ldarg.3
0x9165  stelem.ref
0x9166  ldc.i4   0x643
0x916b  ldstr    aRetrievesingle// "RetrieveSingleRowFromMultipleForCaching"
0x9170  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x9175  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x917a  stloc.s  6
0x917c  leave.s  loc_918A
0x917e  ldloc.s  7
0x9180  brfalse.s loc_9189
0x9182  ldloc.s  7
0x9184  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9189  endfinally
0x918a  ldloc.s  6
0x918c  brfalse.s loc_91E7
0x918e  ldloc.s  6
0x9190  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Count()
0x9195  ldc.i4.0
0x9196  ble.s    loc_91E7
0x9198  ldloc.s  6
0x919a  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x919f  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x91a4  stloc.s  8
0x91a6  br.s     loc_91CE
0x91a8  ldloca.s 8
0x91aa  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x91af  stloc.s  9
0x91b1  ldloc.s  9
0x91b3  ldarg.s  4
0x91b5  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x91ba  castclass [mscorlib]System.String
0x91bf  ldarg.s  5
0x91c1  ldc.i4.5
0x91c2  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x91c7  brfalse.s loc_91CE
0x91c9  ldloc.s  9
0x91cb  stloc.2
0x91cc  leave.s  loc_91E7
0x91ce  ldloca.s 8
0x91d0  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x91d5  brtrue.s loc_91A8
0x91d7  leave.s  loc_91E7
0x91d9  ldloca.s 8
0x91db  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x91e1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x91e6  endfinally
0x91e7  ldloc.2
0x91e8  brfalse.s loc_920A
0x91ea  ldarg.0
0x91eb  ldfld    class Microsoft.Crm.ILocatorCache Microsoft.Crm.ServerLocatorService::_cache
0x91f0  ldloc.0
0x91f1  ldloc.1
0x91f2  ldloc.2
0x91f3  ldloc.2
0x91f4  ldloc.0
0x91f5  callvirt instance class Microsoft.Crm.SharedDatabase.Column Microsoft.Crm.SharedDatabase.Table::get_PrimaryKey()
0x91fa  callvirt instance string Microsoft.Crm.SharedDatabase.Column::get_Name()
0x91ff  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x9204  ldc.i4.0
0x9205  callvirt instance void Microsoft.Crm.ILocatorCache::AddEntry(class Microsoft.Crm.SharedDatabase.Table table, class Microsoft.Crm.Data.PropertyBag conditions, object value, object primaryKey, [opt] bool noExpiration)
0x920a  ldloc.2
0x920b  brfalse.s loc_920F
0x920d  ldloc.2
0x920e  ret
0x920f  ldnull
0x9210  ret
```
