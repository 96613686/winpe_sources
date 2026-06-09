# Microsoft.Crm.Asynchronous.DTAManager::DeleteFiles

- ea: `0x1e50`
- end: `0x1eaa`
- name: `Microsoft.Crm.Asynchronous.DTAManager::DeleteFiles`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1f60`

## callees

- `0x1e50`
- `0x2290`
- `0x22c0`

## pseudocode

```c

```

## disassembly

```asm
0x1e50  ldarg.0
0x1e51  ldfld    string Microsoft.Crm.Asynchronous.DTAManager::_directory
0x1e56  newobj   instance void [System]System.Uri::.ctor(string)
0x1e5b  callvirt instance bool [System]System.Uri::get_IsUnc()
0x1e60  brfalse.s loc_1E86
0x1e62  ldarg.0
0x1e63  ldfld    string Microsoft.Crm.Asynchronous.DTAManager::_fullConfigFilePath
0x1e68  call     void [mscorlib]System.IO.File::Delete(string)
0x1e6d  ldarg.0
0x1e6e  ldfld    string Microsoft.Crm.Asynchronous.DTAManager::_fullOutputFilePath
0x1e73  call     bool [mscorlib]System.IO.File::Exists(string)
0x1e78  brfalse.s loc_1EA9
0x1e7a  ldarg.0
0x1e7b  ldfld    string Microsoft.Crm.Asynchronous.DTAManager::_fullOutputFilePath
0x1e80  call     void [mscorlib]System.IO.File::Delete(string)
0x1e85  ret
0x1e86  ldarg.0
0x1e87  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.DTAManager::_connection
0x1e8c  ldarg.0
0x1e8d  ldfld    string Microsoft.Crm.Asynchronous.DTAManager::_fullConfigFilePath
0x1e92  call     void Microsoft.Crm.Asynchronous.DatabaseTuningUtility::DeleteRemoteFile(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, string fileName)
0x1e97  ldarg.0
0x1e98  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.DTAManager::_connection
0x1e9d  ldarg.0
0x1e9e  ldfld    string Microsoft.Crm.Asynchronous.DTAManager::_fullOutputFilePath
0x1ea3  call     bool Microsoft.Crm.Asynchronous.DatabaseTuningUtility::TryDeleteRemoteFile(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, string fileName)
0x1ea8  pop
0x1ea9  ret
```
