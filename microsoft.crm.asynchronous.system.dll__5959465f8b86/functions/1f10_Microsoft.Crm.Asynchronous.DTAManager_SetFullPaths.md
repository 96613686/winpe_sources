# Microsoft.Crm.Asynchronous.DTAManager::SetFullPaths

- ea: `0x1f10`
- end: `0x1f3e`
- name: `Microsoft.Crm.Asynchronous.DTAManager::SetFullPaths`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1eb0`

## callees

- `0x2230`

## pseudocode

```c

```

## disassembly

```asm
0x1f10  ldarg.0
0x1f11  ldarg.0
0x1f12  ldfld    string Microsoft.Crm.Asynchronous.DTAManager::_directory
0x1f17  ldstr    aXml// ".xml"
0x1f1c  call     string Microsoft.Crm.Asynchronous.DatabaseTuningUtility::GenerateUniqueFileName(string suffix)
0x1f21  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1f26  stfld    string Microsoft.Crm.Asynchronous.DTAManager::_fullConfigFilePath
0x1f2b  ldarg.0
0x1f2c  ldarg.0
0x1f2d  ldfld    string Microsoft.Crm.Asynchronous.DTAManager::_directory
0x1f32  ldarg.1
0x1f33  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1f38  stfld    string Microsoft.Crm.Asynchronous.DTAManager::_fullOutputFilePath
0x1f3d  ret
```
