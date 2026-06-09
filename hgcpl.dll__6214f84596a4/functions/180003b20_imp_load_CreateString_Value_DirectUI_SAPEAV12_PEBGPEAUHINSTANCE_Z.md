# __imp_load_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z

- ea: `0x180003b20`
- end: `0x180003b2c`
- name: `__imp_load_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800030ff`

## import_xrefs

- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x180003b20`

## pseudocode

```c
__int64 load__CreateString_Value_DirectUI__SAPEAV12_PEBGPEAUHINSTANCE_____Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180003b20  lea     rax, __imp_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z; DirectUI::Value::CreateString(ushort const *,HINSTANCE__ *)
0x180003b27  jmp     __tailMerge_dui70_dll
```
