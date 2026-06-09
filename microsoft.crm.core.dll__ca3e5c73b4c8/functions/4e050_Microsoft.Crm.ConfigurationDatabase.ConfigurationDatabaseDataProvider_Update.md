# Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseDataProvider::Update

- ea: `0x4e050`
- end: `0x4e0ca`
- name: `Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseDataProvider::Update`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1b5d0`
- `0x1be80`
- `0x4e050`
- `0x4e0d0`
- `0x648c0`
- `0x64b60`

## string_xrefs

- `0x4e0ad`: `Update`
- `0x4e0b2`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ConfigurationDatabaseDataProvider.cs`
- `0x4e061`: `propertiesToUpdate`
- `0x4e06f`: `At least one property must be specified for update`

## pseudocode

```c

```

## disassembly

```asm
0x4e050  ldarg.1
0x4e051  box      mvar<u1>
0x4e056  ldstr    aObj// "obj"
0x4e05b  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x4e060  ldarg.2
0x4e061  ldstr    aPropertiestoup// "propertiesToUpdate"
0x4e066  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x4e06b  ldarg.2
0x4e06c  ldlen
0x4e06d  brtrue.s loc_4E07A
0x4e06f  ldstr    aAtLeastOneProp// "At least one property must be specified"...
0x4e074  newobj   instance void Microsoft.Crm.CrmInvalidOperationException::.ctor(string message)
0x4e079  throw
0x4e07a  ldtoken  mvar<u1>
0x4e07f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e084  call     string Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseDataProvider::InferTableName(class [mscorlib]System.Type objectType)
0x4e089  stloc.0
0x4e08a  ldarg.1
0x4e08b  call     T0x2B00009E
0x4e090  stloc.1
0x4e091  ldarg.1
0x4e092  ldarg.2
0x4e093  call     T0x2B00009D
0x4e098  stloc.2
0x4e099  call     T0x2B000098
0x4e09e  callvirt instance class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.SharedDatabase.IDatabaseServiceFactory::Config()
0x4e0a3  stloc.3
0x4e0a4  ldloc.3
0x4e0a5  ldloc.0
0x4e0a6  ldloc.1
0x4e0a7  ldloc.2
0x4e0a8  ldc.i4   0x92
0x4e0ad  ldstr    aUpdate// "Update"
0x4e0b2  ldstr    aDA1SSrcPlatfor_37// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4e0b7  callvirt instance int32 Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string tableName, object id, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4e0bc  pop
0x4e0bd  leave.s  loc_4E0C9
0x4e0bf  ldloc.3
0x4e0c0  brfalse.s loc_4E0C8
0x4e0c2  ldloc.3
0x4e0c3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e0c8  endfinally
0x4e0c9  ret
```
