# __imp_load_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z

- ea: `0x1800024aa`
- end: `0x1800024b6`
- name: `__imp_load_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800023b4`

## import_xrefs

- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z` at `0x1800024aa`

## pseudocode

```c
__int64 load__CreateGraphic_Value_DirectUI__SAPEAV12_PEAUHBITMAP____EI_N11_Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x1800024aa  lea     rax, __imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHBITMAP__@@EI_N11@Z; DirectUI::Value::CreateGraphic(HBITMAP__ *,uchar,uint,bool,bool,bool)
0x1800024b1  jmp     __tailMerge_dui70_dll
```
