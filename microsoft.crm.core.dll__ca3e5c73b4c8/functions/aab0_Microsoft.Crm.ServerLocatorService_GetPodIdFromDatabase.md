# Microsoft.Crm.ServerLocatorService::GetPodIdFromDatabase

- ea: `0xaab0`
- end: `0xad38`
- name: `Microsoft.Crm.ServerLocatorService::GetPodIdFromDatabase`
- size: `648`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xaa60`

## callees

- `0x9620`
- `0xa570`
- `0xaab0`
- `0xbdf0`
- `0xbfa0`
- `0x2d9a0`
- `0x43b10`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x44670`
- `0x4d750`
- `0x61520`

## string_xrefs

- `0xaaef`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xabc4`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xacbe`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xaab0  ldc.i4.2
0xaab1  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.ServerLocatorService::GetConfigSku()
0xaab6  beq.s    loc_AABE
0xaab8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xaabd  ret
0xaabe  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xaac3  stloc.0
0xaac4  call     string Microsoft.Crm.EnvironmentWrapper::get_MachineName()
0xaac9  stloc.1
0xaaca  ldarg.0
0xaacb  ldfld    bool Microsoft.Crm.ServerLocatorService::_isRetrieveConditionCacheEnabled
0xaad0  brfalse  loc_AB7B
0xaad5  ldarg.0
0xaad6  ldc.i4.3
0xaad7  stloc.3
0xaad8  ldloca.s 3
0xaada  constrained. Microsoft.Crm.CrmConfigDatabaseTable
0xaae0  callvirt instance string [mscorlib]System.Object::ToString()
0xaae5  ldc.i4   0xA6B
0xaaea  ldstr    aGetpodidfromda// "GetPodIdFromDatabase"
0xaaef  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xaaf4  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xaaf9  dup
0xaafa  brtrue.s loc_AB02
0xaafc  pop
0xaafd  newobj   instance void Microsoft.Crm.Data.PropertyBagCollection::.ctor()
0xab02  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xab07  stloc.s  4
0xab09  br.s     loc_AB62
0xab0b  ldloca.s 4
0xab0d  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0xab12  stloc.s  5
0xab14  ldloca.s 5
0xab16  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0xab1b  ldstr    aName// "Name"
0xab20  callvirt instance bool Microsoft.Crm.Data.PropertyBag::Contains(string propertyName)
0xab25  brfalse.s loc_AB62
0xab27  ldloca.s 5
0xab29  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0xab2e  ldstr    aName// "Name"
0xab33  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xab38  castclass [mscorlib]System.String
0xab3d  ldloc.1
0xab3e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xab43  brfalse.s loc_AB62
0xab45  ldloca.s 5
0xab47  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Value()
0xab4c  ldstr    aPodid// "PodId"
0xab51  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xab56  unbox.any [mscorlib]System.Guid
0xab5b  stloc.s  6
0xab5d  leave    loc_AD35
0xab62  ldloca.s 4
0xab64  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0xab69  brtrue.s loc_AB0B
0xab6b  leave.s  loc_AB7B
0xab6d  ldloca.s 4
0xab6f  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0xab75  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xab7a  endfinally
0xab7b  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xab80  stloc.2
0xab81  ldloc.2
0xab82  ldstr    aName// "Name"
0xab87  ldloc.1
0xab88  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xab8d  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xab92  stloc.s  7
0xab94  ldloc.s  7
0xab96  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0xab9b  ldloc.s  7
0xab9d  ldstr    aServer// "Server"
0xaba2  ldc.i4.1
0xaba3  newarr   [mscorlib]System.String
0xaba8  dup
0xaba9  ldc.i4.0
0xabaa  ldstr    aPodid// "PodId"
0xabaf  stelem.ref
0xabb0  ldc.i4.1
0xabb1  newarr   Microsoft.Crm.Data.PropertyBag
0xabb6  dup
0xabb7  ldc.i4.0
0xabb8  ldloc.2
0xabb9  stelem.ref
0xabba  ldc.i4   0xA7C
0xabbf  ldstr    aGetpodidfromda// "GetPodIdFromDatabase"
0xabc4  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xabc9  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xabce  stloc.s  8
0xabd0  ldloc.s  8
0xabd2  brfalse.s loc_AC35
0xabd4  ldloc.s  8
0xabd6  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0xabdb  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xabe0  stloc.s  9
0xabe2  br.s     loc_AC1C
0xabe4  ldloca.s 9
0xabe6  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0xabeb  stloc.s  0xA
0xabed  ldloc.s  0xA
0xabef  ldstr    aPodid// "PodId"
0xabf4  callvirt instance bool Microsoft.Crm.Data.PropertyBag::Contains(string propertyName)
0xabf9  brfalse.s loc_AC1C
0xabfb  ldloc.s  0xA
0xabfd  ldstr    aPodid// "PodId"
0xac02  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xac07  unbox.any [mscorlib]System.Guid
0xac0c  stloc.0
0xac0d  ldloc.0
0xac0e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xac13  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xac18  brfalse.s loc_AC1C
0xac1a  leave.s  loc_AC43
0xac1c  ldloca.s 9
0xac1e  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0xac23  brtrue.s loc_ABE4
0xac25  leave.s  loc_AC43
0xac27  ldloca.s 9
0xac29  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0xac2f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xac34  endfinally
0xac35  leave.s  loc_AC43
0xac37  ldloc.s  7
0xac39  brfalse.s loc_AC42
0xac3b  ldloc.s  7
0xac3d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xac42  endfinally
0xac43  ldloc.0
0xac44  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xac49  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xac4e  brfalse  loc_AD33
0xac53  ldarg.0
0xac54  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ServerLocatorService::GetScaleGroupId()
0xac59  stloc.s  0xB
0xac5b  ldloc.s  0xB
0xac5d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xac62  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xac67  brfalse  loc_AD33
0xac6c  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xac71  stloc.s  0xC
0xac73  ldloc.s  0xC
0xac75  ldstr    aId// "Id"
0xac7a  ldloc.s  0xB
0xac7c  box      [mscorlib]System.Guid
0xac81  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xac86  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xac8b  stloc.s  0xD
0xac8d  ldloc.s  0xD
0xac8f  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0xac94  ldloc.s  0xD
0xac96  ldstr    aScalegroup// "ScaleGroup"
0xac9b  ldc.i4.1
0xac9c  newarr   [mscorlib]System.String
0xaca1  dup
0xaca2  ldc.i4.0
0xaca3  ldstr    aPodid// "PodId"
0xaca8  stelem.ref
0xaca9  ldc.i4.1
0xacaa  newarr   Microsoft.Crm.Data.PropertyBag
0xacaf  dup
0xacb0  ldc.i4.0
0xacb1  ldloc.s  0xC
0xacb3  stelem.ref
0xacb4  ldc.i4   0xA9D
0xacb9  ldstr    aGetpodidfromda// "GetPodIdFromDatabase"
0xacbe  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xacc3  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.SharedDatabase.DatabaseService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xacc8  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0xaccd  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xacd2  stloc.s  9
0xacd4  br.s     loc_AD0E
0xacd6  ldloca.s 9
0xacd8  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0xacdd  stloc.s  0xE
0xacdf  ldloc.s  0xE
0xace1  ldstr    aPodid// "PodId"
0xace6  callvirt instance bool Microsoft.Crm.Data.PropertyBag::Contains(string propertyName)
0xaceb  brfalse.s loc_AD0E
0xaced  ldloc.s  0xE
0xacef  ldstr    aPodid// "PodId"
0xacf4  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xacf9  unbox.any [mscorlib]System.Guid
0xacfe  stloc.0
0xacff  ldloc.0
0xad00  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xad05  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xad0a  brfalse.s loc_AD0E
0xad0c  leave.s  loc_AD33
0xad0e  ldloca.s 9
0xad10  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0xad15  brtrue.s loc_ACD6
0xad17  leave.s  loc_AD33
0xad19  ldloca.s 9
0xad1b  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0xad21  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xad26  endfinally
0xad27  ldloc.s  0xD
0xad29  brfalse.s loc_AD32
0xad2b  ldloc.s  0xD
0xad2d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xad32  endfinally
0xad33  ldloc.0
0xad34  ret
0xad35  ldloc.s  6
0xad37  ret
```
