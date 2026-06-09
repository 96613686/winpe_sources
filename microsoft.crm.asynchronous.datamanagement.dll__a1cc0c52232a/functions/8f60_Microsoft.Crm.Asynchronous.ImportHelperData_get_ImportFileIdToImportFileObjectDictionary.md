# Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileObjectDictionary

- ea: `0x8f60`
- end: `0x8f67`
- name: `Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportFileIdToImportFileObjectDictionary`
- size: `7`
- prototype: ``
- caller_count: `19`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xbae0`
- `0xbe90`
- `0xd1c0`
- `0xd3d0`
- `0xd4b0`
- `0xd5a0`
- `0xe130`
- `0xe550`
- `0xe9b0`
- `0xfd00`
- `0x10b00`
- `0x14370`
- `0x14ad0`
- `0x16570`
- `0x165d0`
- `0x16690`
- `0x17420`
- `0x19ee0`
- `0x1a2a0`

## pseudocode

```c

```

## disassembly

```asm
0x8f60  ldarg.0
0x8f61  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> Microsoft.Crm.Asynchronous.ImportHelperData::_importFileIdToImportFileObjectDictionary
0x8f66  ret
```
