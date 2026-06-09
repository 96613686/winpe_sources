# __imp_load_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEBGEIGGPEAUHINSTANCE__@@_N2@Z

- ea: `0x1800024ce`
- end: `0x1800024da`
- name: `__imp_load_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEBGEIGGPEAUHINSTANCE__@@_N2@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800023b4`

## import_xrefs

- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEBGEIGGPEAUHINSTANCE__@@_N2@Z` at `0x1800024ce`

## pseudocode

```c
__int64 load__CreateGraphic_Value_DirectUI__SAPEAV12_PEBGEIGGPEAUHINSTANCE_____N2_Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x1800024ce  lea     rax, __imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEBGEIGGPEAUHINSTANCE__@@_N2@Z; DirectUI::Value::CreateGraphic(ushort const *,uchar,uint,ushort,ushort,HINSTANCE__ *,bool,bool)
0x1800024d5  jmp     __tailMerge_dui70_dll
```
