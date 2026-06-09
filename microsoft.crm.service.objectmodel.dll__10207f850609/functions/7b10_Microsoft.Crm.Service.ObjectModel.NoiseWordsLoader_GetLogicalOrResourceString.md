# Microsoft.Crm.Service.ObjectModel.NoiseWordsLoader::GetLogicalOrResourceString

- ea: `0x7b10`
- end: `0x7b1c`
- name: `Microsoft.Crm.Service.ObjectModel.NoiseWordsLoader::GetLogicalOrResourceString`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x7b10`: `Search_Logical_OR_Command`

## pseudocode

```c

```

## disassembly

```asm
0x7b10  ldstr    aSearchLogicalO// "Search_Logical_OR_Command"
0x7b15  ldarg.1
0x7b16  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x7b1b  ret
```
