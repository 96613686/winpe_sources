# Microsoft.Crm.Service.ObjectModel.NoiseWordsLoader::GetLogicalAndResourceString

- ea: `0x7b20`
- end: `0x7b2c`
- name: `Microsoft.Crm.Service.ObjectModel.NoiseWordsLoader::GetLogicalAndResourceString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7b20`: `Search_Logical_AND_Command`

## pseudocode

```c

```

## disassembly

```asm
0x7b20  ldstr    aSearchLogicalA// "Search_Logical_AND_Command"
0x7b25  ldarg.1
0x7b26  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x7b2b  ret
```
