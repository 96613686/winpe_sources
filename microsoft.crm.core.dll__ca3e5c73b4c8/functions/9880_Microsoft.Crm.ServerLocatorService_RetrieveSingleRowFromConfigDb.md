# Microsoft.Crm.ServerLocatorService::RetrieveSingleRowFromConfigDb

- ea: `0x9880`
- end: `0x98ef`
- name: `Microsoft.Crm.ServerLocatorService::RetrieveSingleRowFromConfigDb`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xae80`

## callees

- `0x9880`
- `0xbfa0`
- `0x1a880`
- `0x4a610`
- `0x4d7b0`
- `0x5f5d0`
- `0x607f0`
- `0x61420`

## string_xrefs

- `0x98d6`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x98d1`: `RetrieveSingleRowFromConfigDb`

## pseudocode

```c

```

## disassembly

```asm
0x9880  ldnull
0x9881  stloc.0
0x9882  call     class Microsoft.Crm.SharedDatabase.DBMetadataCache Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::get_Cache()
0x9887  callvirt instance class Microsoft.Crm.SharedDatabase.TableCollection Microsoft.Crm.SharedDatabase.DBMetadataCache::get_Tables()
0x988c  ldarg.1
0x988d  ldloca.s 0
0x988f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.SharedDatabase.Table>::TryGetValue(var<u1>, !!T0)
0x9894  brtrue.s loc_98B1
0x9896  ldstr    aTableWithName// "Table with name '"
0x989b  ldarg.1
0x989c  ldstr    aWasNotFound// "' was not found"
0x98a1  call     string [mscorlib]System.String::Concat(string, string, string)
0x98a6  ldc.i4   0x80040216
0x98ab  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message, int32 errorCode)
0x98b0  throw
0x98b1  ldarg.0
0x98b2  ldfld    valuetype Microsoft.Crm.LocatorServiceContext Microsoft.Crm.ServerLocatorService::_locatorServiceContext
0x98b7  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor(valuetype Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x98bc  stloc.1
0x98bd  ldloc.1
0x98be  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0x98c3  ldloc.1
0x98c4  ldloc.0
0x98c5  callvirt instance string Microsoft.Crm.SharedDatabase.Table::get_Name()
0x98ca  ldarg.2
0x98cb  ldarg.3
0x98cc  ldc.i4   0x76D
0x98d1  ldstr    aRetrievesingle_0// "RetrieveSingleRowFromConfigDb"
0x98d6  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x98db  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveSingleItem(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x98e0  stloc.2
0x98e1  leave.s  loc_98ED
0x98e3  ldloc.1
0x98e4  brfalse.s loc_98EC
0x98e6  ldloc.1
0x98e7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x98ec  endfinally
0x98ed  ldloc.2
0x98ee  ret
```
