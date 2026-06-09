# Microsoft.Crm.Asynchronous.DTAManager::Initialize

- ea: `0x1eb0`
- end: `0x1efb`
- name: `Microsoft.Crm.Asynchronous.DTAManager::Initialize`
- size: `75`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1cd0`
- `0x1cf0`

## callees

- `0x1f00`
- `0x1f10`

## string_xrefs

- `0x1ebc`: `dtaConfigXml`
- `0x1ec7`: `directory`

## pseudocode

```c

```

## disassembly

```asm
0x1eb0  ldarg.1
0x1eb1  ldstr    aConnection// "connection"
0x1eb6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1ebb  ldarg.2
0x1ebc  ldstr    aDtaconfigxml// "dtaConfigXml"
0x1ec1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1ec6  ldarg.3
0x1ec7  ldstr    aDirectory// "directory"
0x1ecc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1ed1  ldarg.s  4
0x1ed3  ldstr    aOutputfilename// "outputFileName"
0x1ed8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1edd  ldarg.0
0x1ede  ldarg.1
0x1edf  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Asynchronous.DTAManager::_connection
0x1ee4  ldarg.0
0x1ee5  ldarg.3
0x1ee6  stfld    string Microsoft.Crm.Asynchronous.DTAManager::_directory
0x1eeb  ldarg.0
0x1eec  ldarg.s  4
0x1eee  call     instance void Microsoft.Crm.Asynchronous.DTAManager::SetFullPaths(string outputFileName)
0x1ef3  ldarg.0
0x1ef4  ldarg.2
0x1ef5  call     instance void Microsoft.Crm.Asynchronous.DTAManager::WriteConfigFile(string dtaConfigXml)
0x1efa  ret
```
