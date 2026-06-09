# Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseDataProvider::Create

- ea: `0x4df70`
- end: `0x4dfd8`
- name: `Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseDataProvider::Create`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1b5d0`
- `0x1be80`
- `0x4df70`
- `0x4e0d0`
- `0x4e110`
- `0x648c0`
- `0x64b30`

## string_xrefs

- `0x4dfbb`: `Create`
- `0x4dfc0`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ConfigurationDatabaseDataProvider.cs`
- `0x4df92`: `Create using extensions object is not allowed`

## pseudocode

```c

```

## disassembly

```asm
0x4df70  ldarg.1
0x4df71  box      mvar<u1>
0x4df76  ldstr    aObj// "obj"
0x4df7b  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x4df80  ldtoken  mvar<u1>
0x4df85  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4df8a  dup
0x4df8b  call     bool Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseDataProvider::IsExtensions(class [mscorlib]System.Type objectType)
0x4df90  brfalse.s loc_4DF9D
0x4df92  ldstr    aCreateUsingExt// "Create using extensions object is not a"...
0x4df97  newobj   instance void Microsoft.Crm.CrmInvalidOperationException::.ctor(string message)
0x4df9c  throw
0x4df9d  call     string Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseDataProvider::InferTableName(class [mscorlib]System.Type objectType)
0x4dfa2  stloc.0
0x4dfa3  ldarg.1
0x4dfa4  ldnull
0x4dfa5  call     T0x2B00009D
0x4dfaa  stloc.1
0x4dfab  call     T0x2B000098
0x4dfb0  callvirt instance class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.SharedDatabase.IDatabaseServiceFactory::Config()
0x4dfb5  stloc.2
0x4dfb6  ldloc.2
0x4dfb7  ldloc.0
0x4dfb8  ldloc.1
0x4dfb9  ldc.i4.s 0x5F
0x4dfbb  ldstr    aCreate// "Create"
0x4dfc0  ldstr    aDA1SSrcPlatfor_37// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4dfc5  callvirt instance object Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4dfca  pop
0x4dfcb  leave.s  loc_4DFD7
0x4dfcd  ldloc.2
0x4dfce  brfalse.s loc_4DFD6
0x4dfd0  ldloc.2
0x4dfd1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4dfd6  endfinally
0x4dfd7  ret
```
