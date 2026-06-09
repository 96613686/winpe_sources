# Microsoft.Crm.Asynchronous.DTAManager::WriteConfigFile

- ea: `0x1f00`
- end: `0x1f0d`
- name: `Microsoft.Crm.Asynchronous.DTAManager::WriteConfigFile`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1eb0`

## pseudocode

```c

```

## disassembly

```asm
0x1f00  ldarg.0
0x1f01  ldfld    string Microsoft.Crm.Asynchronous.DTAManager::_fullConfigFilePath
0x1f06  ldarg.1
0x1f07  call     void [mscorlib]System.IO.File::WriteAllText(string, string)
0x1f0c  ret
```
