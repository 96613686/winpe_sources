# Microsoft.Crm.Asynchronous.ImportOperationImportFile::UpdateCounts

- ea: `0xe960`
- end: `0xe9a5`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::UpdateCounts`
- size: `69`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xe550`
- `0x10b00`

## callees

- `0x42b0`
- `0xe960`

## pseudocode

```c

```

## disassembly

```asm
0xe960  ldarg.3
0xe961  brfalse.s loc_E978
0xe963  ldarg.0
0xe964  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xe969  ldarg.1
0xe96a  ldarg.0
0xe96b  ldfld    string Microsoft.Crm.Asynchronous.ImportOperation::_successCountField
0xe970  ldarg.2
0xe971  ldind.i4
0xe972  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::IncrementImportFileCountField(valuetype [mscorlib]System.Guid importFileId, string countField, int32 incrementValue)
0xe977  ret
0xe978  ldarg.2
0xe979  ldarg.2
0xe97a  ldind.i4
0xe97b  ldc.i4.1
0xe97c  add
0xe97d  stind.i4
0xe97e  ldarg.2
0xe97f  ldind.i4
0xe980  ldarg.0
0xe981  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IConfiguration Microsoft.Crm.Asynchronous.ImportOperation::_configuration
0xe986  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IImportConfiguration::get_CountUpdateBatchSize()
0xe98b  bne.un.s loc_E9A4
0xe98d  ldarg.0
0xe98e  ldfld    class Microsoft.Crm.Asynchronous.ImportDataAccess Microsoft.Crm.Asynchronous.ImportOperation::_importDataAccess
0xe993  ldarg.1
0xe994  ldarg.0
0xe995  ldfld    string Microsoft.Crm.Asynchronous.ImportOperation::_successCountField
0xe99a  ldarg.2
0xe99b  ldind.i4
0xe99c  callvirt instance void Microsoft.Crm.Asynchronous.ImportDataAccess::IncrementImportFileCountField(valuetype [mscorlib]System.Guid importFileId, string countField, int32 incrementValue)
0xe9a1  ldarg.2
0xe9a2  ldc.i4.0
0xe9a3  stind.i4
0xe9a4  ret
```
