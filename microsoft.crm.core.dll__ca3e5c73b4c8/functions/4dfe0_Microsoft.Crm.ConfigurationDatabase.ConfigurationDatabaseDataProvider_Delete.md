# Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseDataProvider::Delete

- ea: `0x4dfe0`
- end: `0x4e046`
- name: `Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseDataProvider::Delete`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1b5d0`
- `0x1be80`
- `0x4dfe0`
- `0x4e0d0`
- `0x4e110`
- `0x648c0`
- `0x64b90`

## string_xrefs

- `0x4e02a`: `Delete`
- `0x4e02f`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\ConfigurationDatabaseDataProvider.cs`
- `0x4e002`: `Delete using extensions object is not allowed`

## pseudocode

```c

```

## disassembly

```asm
0x4dfe0  ldarg.1
0x4dfe1  box      mvar<u1>
0x4dfe6  ldstr    aObj// "obj"
0x4dfeb  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x4dff0  ldtoken  mvar<u1>
0x4dff5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4dffa  dup
0x4dffb  call     bool Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseDataProvider::IsExtensions(class [mscorlib]System.Type objectType)
0x4e000  brfalse.s loc_4E00D
0x4e002  ldstr    aDeleteUsingExt// "Delete using extensions object is not a"...
0x4e007  newobj   instance void Microsoft.Crm.CrmInvalidOperationException::.ctor(string message)
0x4e00c  throw
0x4e00d  call     string Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseDataProvider::InferTableName(class [mscorlib]System.Type objectType)
0x4e012  stloc.0
0x4e013  ldarg.1
0x4e014  call     T0x2B00009E
0x4e019  stloc.1
0x4e01a  call     T0x2B000098
0x4e01f  callvirt instance class Microsoft.Crm.SharedDatabase.IDatabaseService Microsoft.Crm.SharedDatabase.IDatabaseServiceFactory::Config()
0x4e024  stloc.2
0x4e025  ldloc.2
0x4e026  ldloc.0
0x4e027  ldloc.1
0x4e028  ldc.i4.s 0x77
0x4e02a  ldstr    aDelete_0// "Delete"
0x4e02f  ldstr    aDA1SSrcPlatfor_37// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4e034  callvirt instance void Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string tableName, object id, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4e039  leave.s  loc_4E045
0x4e03b  ldloc.2
0x4e03c  brfalse.s loc_4E044
0x4e03e  ldloc.2
0x4e03f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e044  endfinally
0x4e045  ret
```
